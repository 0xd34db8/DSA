### What is BST

- Binary Search Tree = right side > root > left side
- **Inorder** of BST is always in **sorted order**

### Class & Constructor

```cpp
class node{

public:
    int data;
    node* left;
    node* right;

    node(int d)
    {
        this->data = d;
        this->left = nullptr;
        this->right = nullptr;
    }

};
```

### Build a BST

First take input and then insert the input into the tree in a way that creates a valid BST

```cpp
node *insertIntoBST(node *&root, int d)
{
    // base case
    if (root == nullptr)
    {
        root = new node(d);
        return root;
    }

    // if given data is bigger than root => go right
    if (d > root->data)
    {
        root->right = insertIntoBST(root->right, d);
    }

    // else go left
    root->left = insertIntoBST(root->left, d);

    return root;
}

```

| Insertion Complexities | Average Case         | Worst Case       |
| :--------------------- | :------------------- | :--------------- |
| **Time Complexity**    | O(log N)             | O(N)             |
| **Space Complexity**   | O(log N) (recursive) | O(N) (recursive) |
|                        | O(1) (iterative)     | O(1) (iterative) |

```cpp
void takeInput(node *root)
{
    int data;
    cin >> data;

    // take data until -1 is entered
    while (data != -1)
    {
        root = insertIntoBST(root, data);
        cin >> data;
    }
}
```
