### Find Min value in bst

```cpp
    Node* minBST(Node* root) {
        Node* temp = root;

        while(temp != null)
            temp = temp->left;

        return temp;
    }
```

### Find Max value in bst

```cpp
    Node* minBST(Node* root) {
        Node* temp = root;

        while(temp != null)
            temp = temp->right;

        return temp;
    }

```
