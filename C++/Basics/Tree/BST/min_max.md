### Find Min value in bst

```cpp
    Node* minBST(Node* root) {
        if (root == nullptr)
            return nullptr;

        Node* temp = root;

        while(temp->left != nullptr)
            temp = temp->left;

        return temp;
    }
```

### Find Max value in bst

```cpp
    Node* maxBST(Node* root) {
        if (root == nullptr)
            return nullptr;

        Node* temp = root;

        while(temp->right != nullptr)
            temp = temp->right;

        return temp;
    }

```
