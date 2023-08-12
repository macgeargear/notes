**construct tree**
``` cpp
struct Node {
	int key;
	Node* left;
	Node* right;
	Node(int k) {
		key = k;
		left = NULL;
		right = NULL;
	}
}
```

#### Height of a Binary Tree
- if Node is NULL return 0
- recursively call function and plus 1 in the return statement
``` cpp
int heightOfTree(Node* root) {
	if (!root) return 0;
	return 1 + max(heightOfTree(root->left), heightOfTree(root->right));
}
```

#### Print Node at distance K
- if root is `NULL` or `k < 0`-> return
- call function and assign k--
``` cpp
void printNodeAtDistanceK(Node* root, int k) {
	if (!root) return;
	if (k == 0) cout << root->key << " ";
	else {
		printNodeAtDistanceK(root->left, k--);
		printNodeAtDistanceK(root->right, k--);
	}
}
```


