# GitHub Copilot Hackathon

## Challenge 1: Detect, fix, and optimize
These challenges focus on writing efficient Python code by optimizing memory usage and CPU performance. You'll start with basic tasks that highlight common inefficiencies and progressively tackle more advanced optimization techniques. The goal is to develop high-performing code while leveraging GitHub Copilot to assist in detecting issues, refactoring, and implementing more advanced functionality.

## Part 1: Basics of Memory and CPU Optimization

In this section, you'll focus on identifying inefficient code and optimizing it for better memory usage and CPU performance. You'll start with simple examples and gradually move to more complex scenarios.

### Redundant Calculations  
> [!NOTE]  
> Identify and eliminate redundant calculations to improve performance.  
 
```python  
def sum_of_squares(n):  
    result = 0  
    for i in range(n):  
        result += i * i  
    return result  
   
print(sum_of_squares(1000000))  
```  

#### Instructions:  
1. Analyze the Code:  
    - Understand how the `sum_of_squares` function works.  
    - Identify why this implementation might be inefficient.  
3. Optimize the Code:  
    - Make it more efficient.
2. Measure Performance:
    - Use the `time` module to measure how long the execution takes. 
    - Use `%timeit` in a Jupyter notebook to measure execution time. 

---  

### Inefficient Loop  
> [!NOTE]  
> Identify and optimize an inefficient loop to reduce execution time.  

```python  
def find_maximum(numbers):  
    max_num = numbers[0]  
    for num in numbers:  
        if num > max_num:  
            max_num = num  
    return max_num  
   
numbers = [i for i in range(1000000)]  
print(find_maximum(numbers))  
```  
   
#### Instructions:  
1. Analyze the Code:  
    - Understand how the `find_maximum` function works.  
    - Identify why this implementation might be inefficient.  
2. Optimize the Code
3. Measure Performance

---  

### Loops Continued
> [!NOTE]
> Explore the concept of loops further. What native capabilities are there to optimize code that you would sometimes write "manually"?

```python
def sum_list(numbers):  
    total = 0  
    for i in range(len(numbers)):  
        total += numbers[i]  
    return total  
  
numbers = list(range(1, 1000001))

print(sum_list(numbers))
```

#### Instructions:
1. Analyze the Code
2. Optimize the Code
    - Can you optimize the code without using any native functions?
    - What native functionality is the biggest optimization?
    - Would loop unrolling work here? Why, why not?
3. Measure Performance

---

### Efficient Data Structures

> [!NOTE]
> Understand the impact of data structure choices on performance. Replace inefficient data structures with more appropriate ones.

You have a list of unique IDs and need to check if a particular ID exists in the list.

```python
def id_exists(id_list, target_id):
    return target_id in id_list

ids = [i for i in range(1000000)]
print(id_exists(ids, 999999))
```

#### Instructions:

1. Analyze the Code
2. Optimize the Code
3. Measure Performance
4. Generate tests using GitHub Copilot (`@workspace` `/tests`)

### String Concatenation Optimization
> [!NOTE]
> Understand the impact of inefficient string concatenation and optimize it using efficient methods.

```python
def concatenate_strings(string_list):  
    result = ""  
    for s in string_list:  
        result += s  
    return result  
  
string_list = ["string" for _ in range(10000)]  
  
print(concatenate_strings(string_list))
```

#### Instructions:
1. Analyze the Code:
    - Identify why using the `+` operator in a loop for string concatenation is inefficient.
2. Optimize the Code
3. Measure Performance

---

### Memory Efficient Data Storage  
> [!NOTE]  
> Understand the impact of memory-efficient data storage techniques by using more appropriate data structures and data types.
   
#### Inefficient Code Example:  
```python  
def store_large_numbers():  
    large_numbers = [i for i in range(10000000)]  
    return large_numbers  
   
numbers = store_large_numbers()  
print(len(numbers))  
```  
   
#### Instructions:  
1. Analyze the Code  
2. Optimize the Code 
3. Measure Performance

---  

### Handling Large Text Data  
> [!NOTE]  
> Optimize the handling of large text data to reduce memory usage.  
   
#### Inefficient Code Example:  
```python  
def count_word_occurrences(file_path, target_word):  
    with open(file_path, 'r') as file:  
        lines = file.readlines()  
      
    word_count = 0  
    for line in lines:  
        word_count += line.count(target_word)  
      
    return word_count  
  
file_path = 'large_text_file.txt'  
target_word = 'example'  
count = count_word_occurrences(file_path, target_word)  
print(f"The word '{target_word}' occurs {count} times.")  
```  
   
#### Instructions:  
1. Analyze the Code
    - Generate the `large_text_file.txt` file (ask GitHub Copilot how to)
2. Optimize the Code 
3. Measure Performance
4. *Extra: Add support for multiple words to be counted*
5. *Extra: Can you use parallel processing to speed up even more? Why/why not?*

---  

## Part 2: Intermediate Optimization Techniques
In this section, you'll tackle more complex optimization challenges that require advanced techniques and tools. You'll focus on avoiding unnecessary computations, utilizing efficient libraries, and implementing parallel processing for CPU-bound tasks.

### Avoiding Unnecessary Computations

Calculate the Fibonacci sequence up to the nth number.

```python
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(35))
```

#### Instructions:

1. Analyze the Code
2. Optimize the Code
    - Use manual methods to optimize the code
    - Could you use a module like functools to optimize the code?
3. Measure Performance

---

### Lazy Evaluation? Or something else?

```python
def process_strings(data):  
    processed_data = []  
    for item in data:  
        processed_data.append(item.upper() + "_PROCESSED")
    return processed_data  
  

data = ["example_string" for _ in range(1000000)]  
  
processed_data = process_strings(data)  
```

#### Instructions:
1. Analyze the Code
2. Optimize the Code
3. Measure Performance

---

### Utilizing Efficient Libraries
> [!NOTE]
> Leverage optimized libraries like NumPy for computational tasks.

Compute the element-wise sum of two large lists.

Inefficient Code Example:

```python
def list_addition(a, b):
    result = []
    for i in range(len(a)):
        result.append(a[i] + b[i])
    return result

a = [i for i in range(1000000)]
b = [i for i in range(1000000)]
result = list_addition(a, b)
```

#### Instructions:

1. Analyze the Code
2. Optimize the Code
    - Ask GitHub Copilot how to improve code
    - Use NumPy to improve the efficiency.
3. Measure Performance

---

### Efficient Sorting
> [!NOTE]
> Explore efficient sorting algorithms and optimize the code using appropriate sorting methods.

```python
def bubble_sort(data):  
    n = len(data)  
    for i in range(n):  
        for j in range(0, n-i-1):  
            if data[j] > data[j+1]:  
                data[j], data[j+1] = data[j+1], data[j]  
    return data  
  
import random  
data = [random.randint(0, 1000000) for _ in range(10000)]  
  
sorted_data = bubble_sort(data)  
```

#### Instructions:
1. Analyze the Code
2. Optimize the Code
3. Measure Performance
4. Generate unit tests for the final code using GitHub Copilot (`@workspace` `/tests`)
5. *Extra: Create a Jupyter Notebook that compares different sorting algorithms*
6. *Extra: Can sorting be done in parallel? If yes, can you implement that?*

## Part 3: Advanced Optimization Techniques

In this section, you'll tackle more advanced optimization challenges that require parallel processing, memory mapping, and asynchronous I/O. These techniques are essential for improving performance in CPU-bound and I/O-bound tasks.

### Parallel Processing for CPU-bound Tasks

> [!NOTE]
> Implement parallel processing to utilize multiple CPU cores and improve performance of CPU-intensive tasks.

Perform a computationally intensive operation, such as calculating prime numbers in a large range.

#### Instructions:

1. Implement a Function to Check for Primes
2. Optimize the Code
    - How far can you go? GitHub Copilot doesn't automatically give you extreme optimizations if you don't ask for them explicitely.
3. Measure Performance
4. Generate unit tests for the code. The initial set might be limited, work in the editor to add more tests.

---

### Parallel MapReduce
> [!NOTE]
> Implement a parallel MapReduce pattern to process large datasets efficiently.

#### Instructions:
1. Implement a Map Function:
    - Write a function to map input data to intermediate key-value pairs.
2. Implement a Reduce Function:
    - Write a function to reduce intermediate key-value pairs to final results.
3. Optimize the Code:
    - Use multiprocessing to parallelize the MapReduce pattern.
    - Investigate popular external libraries that are used for the complex MapReduce tasks. Ask GitHub copilot about them!
    - Use GitHub Copilot to assist in implementing parallel MapReduce.
4. Measure Performance:
    - Compare execution times between the single-threaded and multi-threaded versions.
5. Generate unit tests

---

### Profiling and Benchmarking

> [!NOTE]
> Use profiling tools to identify bottlenecks and verify the effectiveness of optimizations.

```python
import time  
import random  
from collections import defaultdict  
  
def process_data(data):  
    result = []  
    for item in data:  
        item_str = str(item)  
        item_int = int(item_str)  
          
        if is_prime(item_int):  
            result.append(item_int)  
    return result  
  
def is_prime(n):  
    if n <= 1:  
        return False  
    if n == 2:  
        return True  
    for i in range(2, int(n**0.5) + 1):  
        if n % i == 0:  
            return False  
    return True  
  
def filter_data(data):  
    result = []  
    for item in data:  
        occurrences = count_occurrences(data, item)  
        if occurrences > 1:  
            result.append(item)  
    return result  
  
def count_occurrences(data, value):  
    count = 0  
    for item in data:  
        if item == value:  
            count += 1  
    return count  
  
def aggregate_data(data):  
    total = 0  
    for item in data:  
        total += int(str(item))  
    return total  
  
def longest_common_prefix(strs):  
    if not strs:  
        return ""  
    prefix = strs[0]  
    for s in strs[1:]:  
        while not s.startswith(prefix):  
            prefix = prefix[:-1]  
            if prefix == "":  
                return ""  
    return prefix  
  
def fibonacci(n):  
    if n <= 1:  
        return n  
    return fibonacci(n-1) + fibonacci(n-2)  
 

def main():  
    data = [random.randint(1, 1000) for _ in range(1000)]  
    strings = ["flower", "flow", "flight", "flock"]  
  
    processed_data = process_data(data)  
  
    filtered_data = filter_data(processed_data)  
  
    total = aggregate_data(filtered_data)  
  
    lcp = longest_common_prefix(strings)  
  
    fib_num = fibonacci(30)  
  
    print(f"Total: {total}")  
    print(f"Longest Common Prefix: {lcp}")  
    print(f"Fibonacci(30): {fib_num}")  
  
if __name__ == "__main__":  
    main()
```

#### Instructions:

1. Analyze the Code
2. Optimize the Code
3. Measure Performance
4. Visualize Profiling Data
    - Use tools like snakeviz or pyprof2calltree for visualization.

## Additional Challenges for Advanced Participants

### Memory Mapping Large Files
> [!NOTE]
> Efficiently read and process large files that do not fit into memory using memory mapping.

Instructions:

1. Process a large text file (multiple gigabytes, figure out how to generate one easily using GitHub Copilot) to count the number of lines containing a specific word.
    - Implement Memory Mapping.
    - Use GitHub Copilot to assist in using mmap.

---

### Optimizing Database Queries
> [!NOTE]
> Optimize database queries to improve performance using indexing and query optimization techniques.

**Example 1:**
```sql
SELECT (SELECT department_name FROM departments WHERE department_id = e.department_id) AS dept_name,
       e.employee_id, e.first_name, e.last_name
FROM employees e;
```

**Example 2:**
```sql
SELECT e.employee_id, e.first_name, e.last_name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id
WHERE d.department_name = 'Sales';
```

**Example 3 (order_date is an indexed column):**
```sql
SELECT * FROM orders WHERE YEAR(order_date) = 2023;
```

**Example 4:**
```sql
SELECT * FROM orders WHERE status = 'shipped' OR status = 'delivered';
```

#### Instructions:
1. Analyze the Query:
    - Identify inefficient queries and understand their performance bottlenecks.
2. Optimize the Query:
    - Use indexing, query refactoring, and other optimization techniques.
    - Use GitHub Copilot to assist in optimizing the query.
3. Measure Performance:
    - Compare execution times before and after optimization.

#### Extra:
- Create more examples of inefficient SQL using GitHub Copilot
- Figure out how to measure the optimizations.

---

### Efficient Matrix Multiplication
> [!NOTE]
> Implement efficient matrix multiplication using optimized libraries.

```python
def matrix_multiply_basic(A, B):  
    # Initialize the result matrix with zeros  
    result = [[0 for _ in range(len(B[0]))] for _ in range(len(A))]  
  
    # Perform matrix multiplication  
    for i in range(len(A)):  
        for j in range(len(B[0])):  
            for k in range(len(B)):  
                result[i][j] += A[i][k] * B[k][j]  
  
    return result  
  
# Example 4x4 matrices  
A = [  
    [1, 2, 3, 4],  
    [5, 6, 7, 8],  
    [9, 10, 11, 12],  
    [13, 14, 15, 16]  
]  
  
B = [  
    [16, 15, 14, 13],  
    [12, 11, 10, 9],  
    [8, 7, 6, 5],  
    [4, 3, 2, 1]  
]  
  
# Multiply matrices  
result = matrix_multiply_basic(A, B)  
  
# Print the result  
for row in result:  
    print(row)  
```

#### Instructions:
1. Analyze the Code:
    - Understand the inefficiencies of basic matrix multiplication.
2. Optimize the Code:
    - Use more efficient matrix multiplication approach.
3. Measure Performance:
    - Compare execution times before and after optimization.
        - What about memory usage?
4. Generate unit tests for the code

---

## Asynchronous I/O for I/O-bound Tasks
> [!NOTE]
> Use asynchronous programming to improve performance of I/O-bound operations.

Instructions:

1. Fetch data from multiple URLs concurrently.
    - Implement Async I/O:
        - Use asyncio and aiohttp to perform asynchronous HTTP requests.
        - Use GitHub Copilot to help implement the asynchronous code.
    - Add proper error handling.

---

### Efficient Graph Algorithms
> [!NOTE]
> Optimize graph algorithms for better performance in large graphs.

#### Instructions:
1. Implement a Graph Algorithm:
    - Write a function for a basic graph algorithm like BFS or Dijkstra's.
2. Optimize the Algorithm:
    - Use efficient data structures and algorithms.
    - Use GitHub Copilot to assist in optimizing the graph algorithm.
3. Measure Performance:
    - Compare execution times before and after optimization.
4. Generate unit tests for the code.
