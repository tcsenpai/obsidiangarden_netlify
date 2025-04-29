---
{"dg-publish":true,"permalink":"/bookmarks/management-and-work-related/awk-advanced-text-processing/","tags":["coding","linux","tools","tutorial"]}
---


Let's start by examining the contents of our sample log file. This file contains simulated server access logs that we'll analyze throughout this lab.

First, navigate to the project directory:

```
cd ~/project
```

Now, let's view the first few lines of the log file:

```
head -n 5 server_logs.txt
```

You should see output similar to this:

```
2023-08-01 08:15:23 192.168.1.100 GET /index.html 200
2023-08-01 08:16:45 192.168.1.101 GET /about.html 200
2023-08-01 08:17:30 192.168.1.102 POST /login.php 302
2023-08-01 08:18:12 192.168.1.103 GET /products.html 404
2023-08-01 08:19:05 192.168.1.104 GET /services.html 200
```

This log file contains information about server requests, including the date and time, IP address, HTTP method, requested resource, and status code.

## Basic AWK Usage - Printing Specific Fields

Now that we've seen the structure of our log file, let's use AWK to extract specific information. By default, AWK splits each line into fields based on whitespace. We can refer to these fields using `$1`, `$2`, etc., where `$1` is the first field, `$2` is the second, and so on.

Let's extract the IP addresses (the third field) from our log file:

```
awk '{print $3}' server_logs.txt | head -n 5
```

You should see output similar to this:

```
192.168.1.100
192.168.1.101
192.168.1.102
192.168.1.103
192.168.1.104
```

In this command:

- `awk '{print $3}'` tells AWK to print the third field of each line.
- We pipe (`|`) the output to `head -n 5` to limit the display to the first 5 lines.

Now, let's print both the IP address and the requested resource:

```
awk '{print $3, $5}' server_logs.txt | head -n 5
```

Output:

```
192.168.1.100 /index.html
192.168.1.101 /about.html
192.168.1.102 /login.php
192.168.1.103 /products.html
192.168.1.104 /services.html
```

Here, we're printing the third field (IP address) and the fifth field (requested resource) for each line.

## Filtering Log Entries

One of AWK's strengths is its ability to filter data based on conditions. Let's use this feature to find all POST requests in our log file, as these might be more security-sensitive than GET requests.

Run the following command:

```
awk '$4 == "POST" {print $0}' server_logs.txt
```

This command tells AWK to print the entire line (`$0`) only if the fourth field (`$4`, which is the HTTP method) is equal to "POST".

You should see output similar to this:

```
2023-08-01 08:17:30 192.168.1.102 POST /login.php 302
2023-08-01 09:23:45 192.168.1.110 POST /submit_form.php 200
2023-08-01 10:45:12 192.168.1.115 POST /upload.php 500
```

Now, let's find all requests that resulted in a 404 (Not Found) status:

```
awk '$6 == "404" {print $1, $2, $5}' server_logs.txt
```

This command prints the date, time, and requested resource for all requests with a 404 status code.

Output:

```
2023-08-01 08:18:12 /products.html
2023-08-01 09:30:18 /nonexistent.html
2023-08-01 11:05:30 /missing_page.html
```

These filters can help you quickly identify potential issues or suspicious activities in your server logs.

## Counting and Summarizing Data

AWK is excellent for counting occurrences and summarizing data. Let's use it to count the number of requests for each HTTP status code.

Run this command:

```
awk '{count[$6]++} END {for (code in count) print code, count[code]}' server_logs.txt | sort -n
```

This command might look complex, so let's break it down:

1. `{count[$6]++}`: For each line, increment a counter for the status code (the 6th field).
2. `END {for (code in count) print code, count[code]}`: After processing all lines, print each status code and its count.
3. `| sort -n`: Sort the output numerically.

You should see output similar to this:

```
200 3562
301 45
302 78
304 112
400 23
403 8
404 89
500 15
```

This summary quickly shows you the distribution of status codes in your log file.

Now, let's find the top 5 most frequently accessed resources:

```
awk '{count[$5]++} END {for (resource in count) print count[resource], resource}' server_logs.txt | sort -rn | head -n 5
```

This command works similarly to the previous one, but it counts occurrences of the 5th field (the requested resource) and sorts in reverse numerical order before showing the top 5.

Output:

```
1823 /index.html
956 /about.html
743 /products.html
512 /services.html
298 /contact.html
```

These summaries can help you understand traffic patterns and identify popular (or problematic) resources on your server.

## Creating a Simple Report

For our final task, let's create a simple HTML report summarizing some key information from our log file. We'll use an AWK script stored in a separate file for this more complex operation.

First, create a file named `log_report.awk` with the following content:

> Tips: Copy the content below and paste it into your terminal to create the file.

```
cat << 'EOF' > log_report.awk
BEGIN {
    print "<html><body>"
    print "<h1>Server Log Summary</h1>"
    total = 0
    errors = 0
}

{
    total++
    if ($6 >= 400) errors++
    ip_count[$3]++
    resource_count[$5]++
}

END {
    print "<p>Total requests: " total "</p>"
    print "<p>Error rate: " (errors/total) * 100 "%</p>"

    print "<h2>Top 5 IP Addresses</h2>"
    print "<ul>"
    for (ip in ip_count) {
        top_ips[ip] = ip_count[ip]
    }
    n = asort(top_ips, sorted_ips, "@val_num_desc")
    for (i = 1; i <= 5 && i <= n; i++) {
        for (ip in ip_count) {
            if (ip_count[ip] == sorted_ips[i]) {
                print "<li>" ip ": " ip_count[ip] " requests</li>"
                break
            }
        }
    }
    print "</ul>"

    print "<h2>Top 5 Requested Resources</h2>"
    print "<ul>"
    for (resource in resource_count) {
        top_resources[resource] = resource_count[resource]
    }
    n = asort(top_resources, sorted_resources, "@val_num_desc")
    for (i = 1; i <= 5 && i <= n; i++) {
        for (resource in resource_count) {
            if (resource_count[resource] == sorted_resources[i]) {
                print "<li>" resource ": " resource_count[resource] " requests</li>"
                break
            }
        }
    }
    print "</ul>"

    print "</body></html>"
}
EOF
```

Now, let's run our AWK script to generate the report:

```
awk -f log_report.awk server_logs.txt > log_report.html
```

This command processes the `server_logs.txt` file using our AWK script and saves the output as `log_report.html`.

You can view the contents of the report using the `cat` command:

```
cat log_report.html
```

This report provides a summary of total requests, error rate, top 5 IP addresses, and top 5 requested resources. In a real-world scenario, you could open this HTML file in a web browser for a formatted view.

## Summary

Congratulations! You've completed this lab on using the AWK command for log analysis. Let's recap what you've learned:

1. Basic AWK usage: Printing specific fields from a structured text file.
2. Filtering data: Using conditions in AWK to select specific log entries.
3. Counting and summarizing: Using AWK to generate statistics from log data.
4. Creating reports: Writing more complex AWK scripts to generate formatted reports.

These skills will be invaluable for analyzing log files, processing data, and generating reports in your future work as a system administrator or data analyst.

Here are some additional AWK parameters and features we didn't cover in this lab:

- `-F`: Specifies a field separator other than whitespace.
- `-v`: Assigns a value to a variable.
- `NR`: A built-in variable representing the current record number.
- `NF`: A built-in variable representing the number of fields in the current record.
- `BEGIN` and `END` blocks: Special patterns for initialization and finalization.
- Built-in functions: Mathematical functions, string functions, and more.

Remember, practice is key to mastering AWK. Try modifying the commands and scripts from this lab to analyze different aspects of the log file or to process other types of structured text data.
