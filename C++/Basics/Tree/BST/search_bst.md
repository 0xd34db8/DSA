# Recursive

```cpp
    Node* searchBST(Node* root, int val) {
        // base case
        if (root == nullptr)
            return nullptr;

        if (root->val == val)
            return root;

        // if bigger => go right
        if (val > root->val)
            return searchBST(root->right, val);

        // else go left
        return searchBST(root->left, val);
    }
```

### Complexities(h = height)

- **Time Complexity:** O(h)
- **Space Complexity:** O(h)

# Iterative (Space Constant)

```cpp
    Node* searchBST(Node* root, int val) {
        Node* temp = root;

        while (temp != nullptr) {

            if (temp->val == val)
                return temp;

            // go right
            else if (val > temp->val)
                temp = temp->right;

            // go left
            else
                temp = temp->left;
        }

        return nullptr;
    }
```

### Complexities(h = height)

- **Time Complexity:** O(h)
- **Space Complexity:** O(1)
