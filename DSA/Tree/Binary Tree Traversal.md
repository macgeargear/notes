```cpp
struct Node {
    int key;
    Node* left;
    Node* right;
    Node(int k) {
        key = k;
        left = right = NULL;
    }
};
```

1. **Inorder Traversal**: left -> root -> right
``` cpp
void inorder(Node* root) {
	if (root) {
		inorder(root->left);
		cout << root->key << "\n";
		inorder(root->right);
	}	
}
```

2. **Preorder Traversal**: root -> left -> right
``` cpp
void preorder(Node* root) {
	if (root) {
        cout<<root->key<<" ";
        inorder(root->left);
        inorder(root->right);
    }
}
```

3. **Postorder Traversal**: left -> right -> root
``` cpp
void postorder(Node* root) {
    if (root) {
        inorder(root->left);
        inorder(root->right);
        cout<<root->key<<" ";
    }
}
```

4. **Level order traversal** (using Queue)
``` cpp
void levelOrderTraversal(Node* root) {
	if (!root) return;
	queue<Node*> q;
	q.push(root);
	while (!q.empty()) {
		Node* curr = q.front();
		q.pop();
		cout << curr->key << " ";
		if (curr->left) q.push(curr->left);
		if (curr->right) q.push(curr->right);
		
	}
}
```

1. **Level order traversal (Line by Line)**
- use queue
	- first, push root then push NULL
	- print new line when curr is empty
![[tree]] 
```cpp
void LevelOrderTraversal(Node* root) {
	if (!root) return;
	queue<Node*> q;
	q.push(root);
	q.push(NULL);
	while (q.size() > 1) {
		Node* curr = q.front();
		q.pop();
		if (!curr) {
			cout << "\n";
			q.push(NULL);
			continue;
		}
		cout << curr->key << " ";
		if (curr->left) q.push(curr->left);
		if (curr->right) q.push(curr->right);
	}
}
```
