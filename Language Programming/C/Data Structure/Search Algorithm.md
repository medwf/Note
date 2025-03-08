A `search algorithm` is a step-by-step procedure or formula for solving a problem by systematically exploring and evaluating potential solutions.

Search algorithms are commonly used in computer science and artificial intelligence for tasks such as finding a specific item in a list, locating a path in a graph, or searching for information in a database. Different types of search algorithms are designed for different problem domains and data structures.

## Here are some common types of search algorithms:

### Jump Search Algorithm:

- Description: Jump search is a searching algorithm that works on sorted arrays. It is an improvement over linear search as it jumps ahead by fixed steps instead of traversing the array element by element. The key idea is to divide the array into blocks and perform a linear search in each block to find the approximate location of the target element. Once the block containing the target element is found, a linear search is performed within that block.

Algorithm Steps:

1. Determine the block size, typically denoted as "jump" or "step."
2. Jump through the array in steps of the block size until you find a block where the last element is greater than or equal to the target element.
3. Perform a linear search within that block to find the exact position of the target element.

Time Complexity: The time complexity of jump search is O(√n), where "n" is the size of the array. The primary reason for this complexity is the combination of the jump steps and the linear search within the identified block. The algorithm is efficient for large sorted arrays, but it's not as fast as some other search algorithms like binary search.

Space Complexity: The space complexity of jump search is O(1), indicating constant space usage. The algorithm does not require additional space that grows with the size of the input array. It mainly uses a few variables, such as indices and temporary variables, which remain constant regardless of the array size.

Advantages and Disadvantages:

- Advantages: Jump search is particularly useful when the size of the array is unknown and binary search is not applicable due to the absence of random access (e.g., linked lists).
- Disadvantages: While it is more efficient than linear search, it may not be as fast as binary search in certain cases. Additionally, it assumes a uniformly distributed array, and its performance degrades if the distribution is uneven.

1. Depth-First Search (DFS):

- Description: DFS is an algorithm for traversing or searching tree or graph data structures. It explores as far as possible along each branch before backtracking.
- Applications: Used in pathfinding, topological sorting, and solving puzzles.

3. Breadth-First Search (BFS):

- Description: BFS explores all the vertices at the current depth prior to moving on to vertices at the next depth level.
- Applications: Shortest path finding, network analysis.

1. A Search Algorithm:*

- Description: A* is an informed search algorithm that uses a heuristic to estimate the cost of reaching the goal from a certain node. It combines the advantages of both DFS and BFS.
- Applications: Pathfinding and graph traversal.

1. Hashing:

- Description: Hashing involves using a hash function to map keys or data to a fixed-size array, making it efficient for searching and retrieving data.
- Applications: Database indexing, implementing sets and dictionaries.

3. Interpolation Search:

- Description: Interpolation search is an algorithm for finding a specific value within a range of values. It is particularly useful for uniformly distributed data.

- Time Complexity: O(log log n) on average, but can degrade to O(n) in worst cases.

6. Exponential Search:

- Description: Exponential search is a search algorithm that works on sorted arrays. It involves finding a range where the target element may be present and then using binary search within that range.

- Time Complexity: O(log n)

# Linear Search
- Description: Linear search involves checking each element in a list or array one by one until the target element is found

- Algorithm: # unsored list or sorted list
``` C
-  for index in range(len(array)):

	- You can print here value indexing of list.
	- If array[index] == value:
		Return True, or index where value found.

	- If array[index] > value: # add it to sorted list
		return (false, or -1 mean will not be found)
- return (false, -1 mean that not found)
```
- Time Complexity: O(n)
- Space Complexity: O(1)

# Binary Search
- Description: Binary search is an efficient algorithm for finding a target element in a sorted list or array by repeatedly dividing the search space in half.
- Algorithm: # that only work with sorted list.

```C
Call : Binary_search(array, value, 0, size - 1)

- Def binary_search(array, value, left, right):

- If left == right:
	- Return array[left] == value

- Middle = (left + right) // 2
- If array[middle] == value:
	- Return True
- elif array[middle] > value:
	If left == middle: # nothing to search in left.
		Return false
	Else
		Return binary_search(array, value, left, middle -1)
- Else
	- Return binary_search(array, value, middle + 1, right)
```


```c
int recursive(int *array, int value, size_t left, size_t right)
{
    size_t middle;
    if (left == right)
    {
        printf("Searching in array: %d\n", array[left]);
        if (array[left] == value)
            return (left);
        else
            return (-1);
    }
    middle = (left + right) / 2;
    print_array(array, left, right);
    if (array[middle] == value)
    {
        /*printf("\n");*/
        return (middle);
    }
    else if (array[middle] > value)
    {
        if (left == middle)
        {
            return (-1);
        }
        else
        {
            /*printf("\n");*/
            return (recursive(array, value, left, middle - 1));
        }
    }
    else
    {
        /*printf("\n");*/
        return (recursive(array, value, middle + 1, right));
    }
}
>>> int binary_search(int *array, size_t size, int value)
{
    if (array && size > 0)
        return (recursive(array, value, 0, size - 1));
    return (-1);
}
```
- Time Complexity: O(log n)
- Space Complexity: O(log n)

