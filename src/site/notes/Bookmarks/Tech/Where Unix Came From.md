---
{"dg-publish":true,"permalink":"/bookmarks/tech/where-unix-came-from/","tags":["history","linux","opensource","tools"]}
---


# [Technology history: Where Unix came from | We Love Open Source - All Things Open](https://allthingsopen.org/articles/where-unix-came-from?ref=dailydev)

Learn the origin of many of the Linux commands you use everyday.

- [From prototype to Unix]()
- [Early Unix]()
- [Processing text]()
- [Common roots in Unix]()
- [About the Author]()

---

![IMG-20241106232533463.jpg](/img/user/_resources/Bookmarks/Tech/Where%20Unix%20Came%20From/IMG-20241106232533463.jpg)

Today, you might think of “Unix” and “Linux” as being the same. And for most of what we think of for “Unix” and “Linux” in 2024, that’s close enough.

But Unix has a long history. If you have only known Linux systems, it can be hard to think about “what it was like in the early days of Unix,” because so much has changed since then.

## From prototype to Unix

Let’s take a step back and look at how Unix started. In 1969, a Bell Labs researcher named Ken Thompson was experimenting with operating system design.

Bell Labs had a PDP-7 computer with an interesting peripheral: a very fast (for the time) disk drive. Thompson wanted to see how fast the drive could manage data throughput, so he wrote a custom program to interface with the hard drive. This was no small task; back then, all programming was done in assembly, and creating a hard disk driver required a lot of low-level programming.

At some point, Thompson realized he had put enough work into the interface that he almost had an operating system kernel. He figured that three more weeks would probably get him the rest of the way: a week to write a new editor, a week to create an assembler, and a week to write a prototype kernel. That prototype was the start of the Unix system.

That early prototype was an interesting idea, and Thompson and others at Bell Labs built on it. The single design pattern of the new system was that it should have useful tools that each focused on doing _one_ thing. Brian Kernighan, another researcher at Bell Labs, suggested naming the new system “Unix” – a play on the name “Multics,” an operating system project that Bell Labs had participated in a few years before, but failed due to its complexity.

## Early Unix

By November 1971, Bell Labs collected the programs for the new operating system and created “Unix 1st Edition.” This was followed by Unix 2nd Edition in July 1972, Unix 3rd Edition in February 1973, and Unix 4th Edition in November 1973.

These early Unix versions aren’t too far off from today’s Linux systems. Many of the commands we rely on every day in Linux were already present by Unix 2nd Edition, including `cat` to display files, `mkdir` and `rmdir` to manage directories, `cp`, `mv`, and `rm` to manage files, `chmod` and `chown` to manage file access, `df` and `du` to examine disk space usage, `ls` and `chdir` (like `cd`) to navigate files, as well as a host of other familiar commands like `cmp`, `date`, `echo`, `find`, `ln`, `man`, `mount` and `umount`, `sort`, `wc`, and `who`.

---

Here’s a [handy reference to all of the section 1 commands](https://allthingsopen.org/articles/unix-4th-edition-commands-reference-guide) from the Unix 4th Edition manual. The manual was divided into separate sections, and section 1 was reserved for general user commands:

1. User commands
2. System calls
3. Programming routines
4. Special files
5. File formats
6. User-maintained programs
7. Miscellaneous entries
8. Maintenance

You may be familiar with many of these commands. Most still exist in modern Linux  
systems, but a few have been replaced with other commands that do pretty much the

same thing (like

`ar` to make archives; you probably use `zip` or `tar` instead).

|             |                                          |
| ----------- | ---------------------------------------- |
| **Command** | **What it does**                         |
| ar          | create archives                          |
| cat         | concatenate files                        |
| chdir       | change directory                         |
| chmod       | change mode                              |
| cmp         | compare files                            |
| comm        | print common lines                       |
| cp          | copy files                               |
| date        | print date                               |
| dc          | desktop calculator                       |
| du          | disk usage                               |
| echo        | print output                             |
| ed          | editor                                   |
| exit        | exit the shell                           |
| file        | print file type                          |
| goto        | shell scripting command                  |
| grep        | search for text                          |
| if          | shell scripting command                  |
| kill        | terminate processes                      |
| ln          | create links                             |
| login       | sign into the system                     |
| ls          | list files                               |
| mail        | send email                               |
| man         | manual pages                             |
| merge       | combine files                            |
| mesg        | allow or deny messages                   |
| mkdir       | create directories                       |
| mv          | move files                               |
| nice        | run at low priority                      |
| nohup       | run command without hangups              |
| nroff       | document preparation (new roff)          |
| passwd      | set password                             |
| pr          | print files                              |
| ps          | process status                           |
| rm          | remove files                             |
| rmdir       | remove directories                       |
| roff        | document preparation (replaced by nroff) |
| sh          | command shell                            |
| shift       | adjust command line arguments            |
| sleep       | wait for an interval                     |
| sort        | sort a file                              |
| split       | break up a file                          |
| stty        | set TeleType options                     |
| sum         | checksum                                 |
| time        | how long it takes to run a command       |
| tr          | transliterate text                       |
| troff       | document processor (typesetter roff)     |
| tty         | get TeleType name                        |
| uniq        | remove repeated lines                    |
| wait        | wait for a job to finish                 |
| wc          | word count                               |
| who         | list currently logged in users           |
| write       | send terminal message to a user          |

These other _section 1_ commands were useful for programming.

|             |                            |
| ----------- | -------------------------- |
| **Command** | **What it does**           |
| as          | assembler                  |
| bas         | BASIC programming          |
| cc          | C compiler                 |
| cdb         | C debugger                 |
| cref        | cross reference listing    |
| db          | debugger                   |
| fc          | FORTRAN compiler           |
| ld          | linker                     |
| nm          | print name list            |
| od          | octal dump                 |
| size        | the size of an object file |
| sno         | SNOBOL interpreter         |
| strip       | remove symbols             |

These other _section 1_ commands from Unix 4th Edition were specific to the Bell Labs environment. If you don’t recognize these, that’s because they were later dropped:

|             |                                               |
| ----------- | --------------------------------------------- |
| **Command** | **What it does**                              |
| catsim      | simulate a phototypesetter on a terminal      |
| dsw         | delete interactively                          |
| fed         | form letter editor                            |
| form        | form letter generator                         |
| opr         | offline print to Honeywell 6070               |
| pfe         | print floating exceptions                     |
| plot        | make charts on a terminal                     |
| proof       | compare text files (like diff)                |
| rew         | rewind a tape                                 |
| speak       | text to speech                                |
| tp          | manage tapes                                  |
| tss         | connect to MH-TSS on Honeywell 6070           |
| type        | print files to the TeleType like a typewriter |
| typo        | find spelling errors                          |

---

The early Unix also included other commands that still exist but aren’t often used, such as `ar` to archive files, `dc` as the desktop calculator, `ed` to edit files, and `sum` to perform checksums. Unix 2nd Edition also supported early concepts of email with `mail`, and a kind of instant messaging with `mesg` and `write` to send messages to each others’ terminals.

Programmers on the early Unix had a variety of compilers and tools to help them create new programs, including `as` to assemble programs, `bas` for BASIC programming, `cc` (C compiler), `db` (debugger), `fc` (FORTRAN compiler), `ld` (linker), `nm` (name list), `od` (octal dump), `strip` (remove symbols), and `un` (find undefined symbols). You may recognize these tools on today’s Linux systems, although you might use different names for them, such as `gcc` for compiling C programs.

Some Unix commands changed over time, but we can still recognize their early predecessors in Unix 2nd Edition: The `sh` shell supported early versions of : labels, `goto`, and `if` statements–today, you might use Bash for your shell, which does all that and more. The `roff` program was an early document preparation system, a simplified implementation based on another program called RUNOFF from a few years before. The `check` and `salve` commands provided similar filesystem checks as `fsck`, `dsw` deleted files like `rm -i,``istat` provided inode status, `m6` was an early macro processor similar to today’s `m4`, and `tm` displayed system time and uptime information.

Other commands in this early Unix were relics of their time, dedicated to supporting systems that no longer exist. For example, the Unix 2nd Edition manual describes tools to communicate with a Honeywell 6070 mainframe computer, including `dpd` (data phone daemon), `tss` (communicate with the time sharing system), and `opr` (print files “offline” to the Honeywell 6070 system).

## Processing text

After Unix 1st Edition, Thompson looked for a more powerful system to keep working on Unix. Unfortunately, management didn’t want to invest in operating system research, having felt burned out by the failed Multics partnership. They turned down the request to purchase a new computer system.

But the Unix team found a workaround. Around the same time, the Legal department wanted to purchase a new document preparation system so they could produce patent applications, which required specific formatting. However, the new software they planned to buy wasn’t ready. The Unix team struck a deal: the patents team would purchase a new PDP-11 for the Unix team, and the Unix team would update the `roff` text processing system to support the necessary features to write patent applications.

And technically, no one would be working on operating system research.

That’s why Unix 2nd edition also included a range of document processing and printing tools, including `nroff` (the _new_ version of `roff`), `ov` to overlay printed pages, `pr` as a print preprocessor, and `type` to print pages on a TeleType like a typewriter.

Later, when the Labs purchased a phototypesetter, the Unix team rewrote `nroff` to become `troff` (the _typesetter_ version of `roff`), included in Unix 4th Edition. Other text processing tools supported `troff`, such as `eqn` to generate equations for scientific documents and `tbl` to format tables.

Other Unix features that we consider commonplace today appeared in following versions of Unix. One notable example is the ability to redirect the output of one command into another using _pipes_, which first appeared in Unix 3rd Edition. With pipes came new programs to act as filters, including `grep` to search for matching text in files (Unix 4th Edition) and `tee` to save the intermediate output of piped commands (Unix 5th Edition). The more feature-rich Bourne Shell finally replaced `sh` in Unix 7th Edition.

## Common roots in Unix

We don’t often think about the origins of the Linux commands we use every day. These commands originated in a time when computers were slow and memory was measured in _kilobytes_. The tools needed to be small and focused.

One thing that’s changed from original Unix to today’s Linux systems is the breadth of command line options. With more memory and faster computers, each tool can take on more work. For example, the `ls` command from Unix 2nd Edition supported just five options: `-l` to list in _long_ format, `-t` to sort by time instead of name, `-a` to list all files, `-s` to show file sizes, and `-d` to list directory names instead of their contents. The modern GNU `ls` command supports these original options, plus over fifty extensions.

Today, every Unix-like system can trace their ancestry back to the original Unix. That includes Linux, which uses the GNU tools – and the GNU tools are based on the Unix tools. Linux in 2024 is removed from the original Unix design, and for good reason – Linux supports architectures and tools not dreamt of during the original Unix era. But the core command line experience in Linux is still very similar to the Unix command line of the 1970s. The next time you use ls to list the files in a directory, remember that you’re using a command line that’s been with us for more than fifty years.

## About the Author

Jim Hall is an open source software advocate and developer, best known for usability testing in GNOME and as the founder + project coordinator of FreeDOS. At work, Jim is CEO of Hallmentum, an IT executive consulting company that provides hands-on IT Leadership training, workshops, and coaching.

[Read Jim's Full Bio](https://allthingsopen.org/authors/jim-hall)

The opinions expressed on this website are those of each author, not of the author's employer or All Things Open/We Love Open Source.
