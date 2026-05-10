---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 20:45:24
learned at: 09-05-2026
last repetaed at: 09-05-2026
---
```
	function recursiveInsertIntoBST(root, val) {
		if (!root) {
			return new TreeNode(val);
		}
		
		if (val > root.val) {
			root.right = recursiveInsertIntoBST(root.right, val);
		} else {
			root.left = recursiveInsertIntoBST(root.left, val);
		}
		
		return root;
	}
	
	function iterativeInsertIntoBst(root, val) {
		const newTreeNode = new TreeNode(val);

        if (!root) {

            return newTreeNode;

        }

        let cur = root;

        while (true) {

            if (val > cur.val) {

                if (!cur.right) {

                     cur.right = newTreeNode;

                     return root;

                }

                cur = cur.right;

            } else {

                if (!cur.left) {

                    cur.left = newTreeNode;

                    return root;

                }

                cur = cur.left;

            }

        }
	}
	
	function deleteFromBst(root, key) {
		if (!root) {
			return root;
		}
		
		if (key > root.val) {
			root.right = deleteNode(root.right, key);
		} else if (key < root.val) {
			root.left = deleteNode(root.left, key)
		} else {
			if (!root.left) return root.right;
			if (!root.right) return root.left;
			
			let cur = root;
			while (cur.right) {
				cur = cur.right;
			}
			
			root.val = cur.val;
			root.right = deleteNode(root.right, root.val);
		}
		
		return root;		 
	}

```


Rel:
Tags: #algoritms, #bst
