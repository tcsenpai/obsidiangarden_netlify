---
{"dg-publish":true,"permalink":"/bookmarks/tech/algorithms-in-python/","tags":["algorithm","coding","halloffame","technique","tutorial"]}
---


![_resources/Algorithms In Python/8576a9d676314f3b1286dad26dbb9f3d_MD5.jpg](/img/user/_resources/Algorithms%20In%20Python/8576a9d676314f3b1286dad26dbb9f3d_MD5.jpg)

Algorithms in Python

Algorithms are the step-by-step instructions that solve problems or perform tasks. Broadly, we can classify algorithms into categories based on their purpose, such as sorting, searching, graph traversal, and optimization. Python is a great language to learn and implement algorithmic code.

## Types of Algorithms

**Sorting Algorithms**  
Used to arrange data in a specific order. Examples include:

- Bubble Sort
- Quick Sort
- Merge Sort
- Heap Sort

**Searching Algorithms**  
Used to find specific data within a dataset. Examples include:

- Linear Search
- Binary Search
- Depth-First Search (DFS)
- Breadth-First Search (BFS)

**Graph Algorithms**  
Solve problems related to graphs (networks of nodes and edges). Examples include:

- Dijkstra’s Algorithm (shortest path)
- Floyd-Warshall Algorithm
- Kruskal’s Algorithm (minimum spanning tree)
- Prim’s Algorithm

**Backtracking Algorithms**  
Solve problems recursively by trying all possibilities and undoing steps when needed. Examples include:

- N-Queens Problem
- Sudoku Solver
- Maze Solver

**Compression Algorithms**  
Reduce data size for storage or transmission. Examples include:

- Huffman Coding
- Run-Length Encoding (RLE)
- Arithmetic Coding
- Lempel-Ziv-Welch (LZW)

**Divide and Conquer Algorithms**  
Break problems into smaller subproblems, solve them independently, and combine the results. Examples include:

- Merge Sort
- Quick Sort
- Binary Search

**Dynamic Programming Algorithms**  
Solve problems by breaking them into overlapping subproblems and reusing solutions. Examples include:

- Fibonacci Sequence
- Longest Common Subsequence (LCS)
- Knapsack Problem

**Greedy Algorithms**  
Make locally optimal choices at each step to find a global solution. Examples include:

- Activity Selection
- Huffman Coding
- Dijkstra’s Algorithm (can also be considered greedy)

**String Matching and Manipulation Algorithms**  
Used for text searching and manipulation. Examples include:

- KMP (Knuth-Morris-Pratt) Algorithm
- Rabin-Karp Algorithm
- Boyer-Moore Algorithm

**Optimization Algorithms**  
Focus on finding the best solution to a problem. Examples include:

- Linear Programming
- Genetic Algorithms
- Simulated Annealing

**Recursive Algorithms**  
Solve problems by calling themselves with smaller input. Examples include:

- Factorial Calculation
- Tower of Hanoi
- Fibonacci Sequence

**Numerical Algorithms**  
Used for performing mathematical computations. Examples include:

- Newton-Raphson Method
- Gaussian Elimination
- Fast Fourier Transform (FFT)

**Machine Learning Algorithms**  
Used for predictions, classifications, and clustering. Examples include:

- Linear Regression
- Decision Trees
- k-Means Clustering

**Cryptographic Algorithms**  
Ensure data security and encryption. Examples include:

- RSA Algorithm
- AES (Advanced Encryption Standard)
- SHA (Secure Hash Algorithms)

**Brute Force Algorithms**  
Try all possible solutions to find the correct one. Examples include:

- Password Cracking
- Subset Sum Problem

**Randomized Algorithms**  
Use random numbers to make decisions during execution. Examples include:

- Randomized Quick Sort
- Monte Carlo Methods

**Traversal Algorithms**  
Traverse data structures like trees and graphs. Examples include:

- Inorder, Preorder, Postorder Traversal (trees)
- BFS and DFS (graphs)

## But what makes an Algorithm and Algorithm?

Below, we dive into the essential characteristics of algorithms and explore their practical application through example code, shedding light on what sets these systematic procedures apart from coded instructions.

## Characteristics of an Algorithm:

**Definiteness**  
Every step in the algorithm is clearly defined and unambiguous. The sequence of operations must leave no room for interpretation, ensuring a systematic and consistent execution. For example:

- Breaking a problem into smaller subproblems.
- Recursively solving each subproblem.
- Combining the results to achieve the final solution.

**Input**  
An algorithm must accept well-defined input values. These inputs are the starting point for the algorithm’s operations. For example:

- A dataset to be processed.
- A query to be resolved.
- Parameters that guide the behavior of the algorithm.

**Output**  
An algorithm produces a meaningful output that satisfies the problem it is designed to solve. The output must be related to the input and provide a clear result. For example:

- A sorted version of a dataset.
- The shortest path between two points.
- A decision or prediction based on given data.

**Finiteness**  
The algorithm must terminate after a finite number of steps. It cannot run indefinitely and must have a defined endpoint. For example:

- Recursion stops when a base case is reached.
- Iterations stop when a condition is no longer satisfied.

**Effectiveness**  
Each operation in the algorithm is simple, basic, and can be executed within a finite amount of time. The steps should be feasible with the available resources and tools. For example:

- Performing arithmetic calculations.
- Comparing elements in a list.
- Storing or updating values in memory.

## Let’s break apart the python samples below…

## Sorting Algorithms

Sorting algorithms are essential for organizing data. Python’s `sorted()` and `.sort()` are efficient, but understanding the core concepts is important.

## Example: Merge Sort

```
def merge_sort(arr):    if len(arr) > 1:        mid = len(arr) // 2        left_half = arr[:mid]        right_half = arr[mid:]        merge_sort(left_half)        merge_sort(right_half)        i = j = k = 0        while i < len(left_half) and j < len(right_half):            if left_half[i] < right_half[j]:                arr[k] = left_half[i]                i += 1            else:                arr[k] = right_half[j]                j += 1            k += 1        while i < len(left_half):            arr[k] = left_half[i]            i += 1            k += 1        while j < len(right_half):            arr[k] = right_half[j]            j += 1            k += 1data = [38, 27, 43, 3, 9, 82, 10]merge_sort(data)print("Sorted array:", data)
```

## 1\. Definiteness

Each step of the `merge_sort` function is clearly defined and unambiguous:

**Dividing the Array**:  
The function splits the input array into two halves:

```
mid = len(arr) // 2left_half = arr[:mid]right_half = arr[mid:]
```

- This ensures the array is divided precisely into two parts for further processing.

**Recursive Sorting**:  
Each half of the array is recursively sorted:

```
merge_sort(left_half)merge_sort(right_half)
```

- This process continues until the base case is reached (a single-element array), which is inherently sorted.

**Merging the Halves**:  
After sorting the two halves, the function merges them:

```
while i < len(left_half) and j < len(right_half):    if left_half[i] < right_half[j]:        arr[k] = left_half[i]        i += 1    else:        arr[k] = right_half[j]        j += 1    k += 1
```

The merging process is systematic and ensures the final array is sorted.

## 2\. Input

The algorithm accepts an **unsorted list** as its input.  
For example:

```
data = [38, 27, 43, 3, 9, 82, 10]
```

This input list is processed through the steps of division, recursion, and merging.

## 3\. Output

The function produces a **sorted version** of the input list as output.  
For example:

```
print("Sorted array:", data)
```

Output:

```
Sorted array: [3, 9, 10, 27, 38, 43, 82]
```

The output is meaningful and directly satisfies the purpose of sorting.

## 4\. Finiteness

The algorithm terminates after a finite number of steps:

**Base Case**:  
The recursion ends when the array contains one or fewer elements:

```
if len(arr) > 1:
```

This ensures the recursion does not continue indefinitely.

**Merging Process**:  
The merging process is bounded by the length of the array, ensuring it completes in a finite time.

The recursive nature of the function guarantees eventual termination as the array is divided into smaller parts until the base case is reached.

## 5\. Effectiveness

Every operation in the algorithm is straightforward and executable within a finite amount of time:

**Dividing the Array**:  
Slicing the array into two halves is a direct operation:

```
left_half = arr[:mid]right_half = arr[mid:]
```

**Comparing Elements**:  
The merging step involves simple comparisons to determine the correct order:

```
if left_half[i] < right_half[j]:    arr[k] = left_half[i]
```

**Copying Values**:  
Remaining elements in either `left_half` or `right_half` are copied back into the main array:

```
while i < len(left_half):    arr[k] = left_half[i]    i += 1
```

Each of these operations is finite and efficient.

## Searching Algorithms

Searching is the foundation of many real-world systems, from databases to web search engines.

## Example: Binary Search

```
def binary_search(arr, target):    low, high = 0, len(arr) - 1    while low <= high:        mid = (low + high)         if arr[mid] == target:            return mid        elif arr[mid] < target:            low = mid + 1        else:            high = mid - 1    return -1data = [3, 9, 10, 27, 38, 43, 82]target = 27result = binary_search(data, target)print("Target found at index:", result)
```

## 1\. Definiteness

Each step of the `binary_search` function is clearly defined and unambiguous:

**Initialization**:  
The variables `low` and `high` define the current search range:

```
low, high = 0, len(arr) - 1
```

**Midpoint Calculation**:  
The midpoint of the current range is calculated:

```
mid = (low + high) // 2
```

**Comparison**:  
The value at `arr[mid]` is compared to the target:

- If `arr[mid] == target`, the target is found, and the index is returned.
- If `arr[mid] < target`, the search range is adjusted to the right half (`low = mid + 1`).
- If `arr[mid] > target`, the search range is adjusted to the left half (`high = mid - 1`).

**Termination**:  
The loop ends when the target is found or the search range becomes invalid (`low > high`), returning `-1` to indicate the target was not found.

## 2\. Input

The algorithm accepts two inputs:

- `arr`: A sorted list of elements.  
   Example: `data = [3, 9, 10, 27, 38, 43, 82]`
- `target`: The value to search for.  
   Example: `target = 27`

## 3\. Output

The function produces an index of the `target` in the array if it exists. Otherwise, it returns `-1` to indicate the target is not present.

For the example:

```
result = binary_search(data, target)print("Target found at index:", result)
```

Output:

```
Target found at index: 3
```

The result is meaningful and satisfies the purpose of locating the target value.

## 4\. Finiteness

The algorithm terminates after a finite number of steps:

- The search range (`low` to `high`) is halved at each iteration.
- The loop condition `low <= high` ensures the process stops when the range becomes invalid.

For a list of nnn elements, the maximum number of iterations is ⌈log⁡2(n)⌉\\lceil \\log_2(n) \\rceil⌈log2(n)⌉, which is finite.

## 5\. Effectiveness

Each operation in the algorithm is basic and executable within a finite amount of time:

- **Midpoint Calculation**:  
   Simple integer arithmetic is used to calculate the midpoint:

```
mid = (low + high) // 2
```

**Comparison**:  
Checking `arr[mid] == target` and adjusting the range (`low` or `high`) are straightforward operations:

```
if arr[mid] == target:    return midelif arr[mid] < target:    low = mid + 1else:    high = mid - 1
```

**Return Value**:  
If the loop terminates without finding the target, the function returns `-1`:

```
return -1
```

All operations are simple and execute in constant time within each iteration of the loop.

## Dijkstra’s Algorithm

Dijkstra’s algorithm finds the shortest path in a graph, useful in navigation systems.

```
import heapqgraph = {    "A": {"B": 1, "C": 4},    "B": {"A": 1, "C": 2, "D": 5},    "C": {"A": 4, "B": 2, "D": 1},    "D": {"B": 5, "C": 1},}def dijkstra(graph, start):    distances = {node: float('inf') for node in graph}    distances[start] = 0    priority_queue = [(0, start)]    while priority_queue:        current_distance, current_node = heapq.heappop(priority_queue)        for neighbor, weight in graph[current_node].items():            distance = current_distance + weight            if distance < distances[neighbor]:                distances[neighbor] = distance                heapq.heappush(priority_queue, (distance, neighbor))    return distancesprint("Shortest paths:", dijkstra(graph, "A"))
```

## 1\. Definiteness

Each step in the algorithm is clearly defined and unambiguous:

- **Initialization**:  
   Distances to all nodes are initialized to infinity (`float('inf')`), except the starting node, which is set to `0`. A priority queue is initialized with the starting node:

```
distances = {node: float('inf') for node in graph}distances[start] = 0priority_queue = [(0, start)]
```

**Main Loop**:  
While the priority queue is not empty:

- The node with the smallest distance is popped from the queue.
- Its neighbors are processed to update their distances:

```
current_distance, current_node = heapq.heappop(priority_queue)for neighbor, weight in graph[current_node].items():    distance = current_distance + weight    if distance < distances[neighbor]:        distances[neighbor] = distance        heapq.heappush(priority_queue, (distance, neighbor))
```

**Termination**:  
When the priority queue is empty, all nodes have been processed, and the function returns the shortest distances:

```
return distances
```

## 2\. Input

The algorithm accepts two inputs:

1.  `graph`: A dictionary representing a weighted graph where:

- Keys are node labels.
- Values are dictionaries of neighbors and their respective edge weights.  
   Example:

```
graph = {    "A": {"B": 1, "C": 4},    "B": {"A": 1, "C": 2, "D": 5},    "C": {"A": 4, "B": 2, "D": 1},    "D": {"B": 5, "C": 1},}
```

`start`: The starting node for calculating shortest paths.  
Example:

```
start = "A"
```

## 3\. Output

The function produces a dictionary of the shortest distances from the starting node to all other nodes in the graph. For the given input:

```
print("Shortest paths:", dijkstra(graph, "A"))
```

Output:

```
Shortest paths: {'A': 0, 'B': 1, 'C': 3, 'D': 4}
```

This output is meaningful, as it satisfies the purpose of finding the shortest path distances.

## 4\. Finiteness

The algorithm terminates after a finite number of steps:

- The main loop processes each node exactly once when it is popped from the priority queue.
- Each neighbor of a node is processed only when a shorter path is found, which is finite for a graph with a fixed number of edges.

## 5\. Effectiveness

Every operation in the algorithm is basic and executable within a finite amount of time:

- **Initializing Distances**:  
   This is a straightforward operation:

```
distances = {node: float('inf') for node in graph}
```

**Using Priority Queue**:  
The priority queue is implemented using Python’s `heapq`, ensuring efficient extraction of the smallest distance:

```
current_distance, current_node = heapq.heappop(priority_queue)
```

**Updating Distances**:  
Distance calculations involve simple arithmetic:

```
distance = current_distance + weightif distance < distances[neighbor]:    distances[neighbor] = distance
```

**Adding Nodes to the Queue**:  
Nodes are added to the priority queue with their updated distances:

```
heapq.heappush(priority_queue, (distance, neighbor))
```

Thank you for reading this article. I hope you found it helpful and informative. If you have any questions, or if you would like to suggest new Python code examples or topics for future tutorials, please feel free to reach out. Your feedback and suggestions are always welcome!

Happy coding!  
C. C. Python Programming
