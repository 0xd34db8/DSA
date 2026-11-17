- A dynamic array

- Has the ability to resize itself automatically when an element is inserted or deleted.

- Store collection of elements of same type in contiguous memory

| Space complexity |
| ---------------- |
| O(n)             |

| Operation                 | Time Complexity                 |
| ------------------------- | ------------------------------- |
| Access                    | O(1)                            |
| Insert (end)              | Amortized O(1), Worst-case O(n) |
| Insert (beginning/middle) | O(n)                            |
| Delete (end)              | O(1)                            |
| Delete (beginning/middle) | O(n)                            |

`pushback`

 insert the element passed in the parameter in the vectors, the element is inserted at the end.

`popback`

removes the last element from the vector

`front`

 Returns a reference to the first element of the vector.

`back`

Returns a reference to the last element of the vector.

`capacity`

returns the current capacity of the vector.

In C++, you declare a vector using the `vector` STL container.

First, include the header:

```cpp
#include <vector>
using namespace std;
```

## **1. Different ways to declare vectors**

```cpp
// Empty vector
vector<int> v;

// Vector with 5 elements, initialized to 0
vector<int> v(5);

// Vector with 5 elements, initialized to 10
vector<int> v(5, 10);

// Vector with predefined elements
vector<int> v = {1, 2, 3, 4, 5};

// Another way
vector<int> v{1, 2, 3, 4, 5};
```

## **2. Common vector operations**

```cpp
vector<int> v;

v.push_back(10);       // Add element at end
v.push_back(20);

v.pop_back();          // Remove last element

v.size();              // Number of elements
v.empty();             // Check if empty

v[0];                  // Access element (no bounds checking)
v.at(0);               // Access element (bounds checking)

v.front();             // First element
v.back();              // Last element

v.clear();              // Remove all elements
```

## **3. 2D Vector**

```cpp
// 3 rows and 4 columns, initialized to 0
vector<vector<int>> matrix(3, vector<int>(4, 0));

// Predefined 2D vector
vector<vector<int>> matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

## **4. Iterating through a vector**

```cpp
vector<int> v = {10, 20, 30, 40};

// Normal loop
for (int i = 0; i < v.size(); i++) {
    cout << v[i] << " ";
}

// Range-based loop
for (int x : v) {
    cout << x << " ";
}

// Using iterators
for (auto it = v.begin(); it != v.end(); it++) {
    cout << *it << " ";
}
```

## **5. Other useful declarations**

| Declaration             | Meaning          |
| ----------------------- | ---------------- |
| `vector<int>`           | Integer vector   |
| `vector<char>`          | Character vector |
| `vector<string>`        | String vector    |
| `vector<bool>`          | Boolean vector   |
| `vector<long long>`     | Long long vector |
| `vector<pair<int,int>>` | Vector of pairs  |
| `vector<vector<int>>`   | 2D vector        |

**Most commonly used in LeetCode:**

```cpp
vector<int> nums;
vector<int> nums(n, 0);
vector<vector<int>> adj(n);
vector<vector<int>> matrix(m, vector<int>(n, 0));
```

`vector<vector<int>> adj(n)` is particularly common in Graph and DFS/BFS problems.
