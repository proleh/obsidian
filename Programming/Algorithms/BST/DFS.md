---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 20:19:15
learned at: 09-05-2026
last repetaed at: DFS
---
Rel:
Tags:  #algoritms, #bst


```
function dfsIterative(root) {
	  const res = [];

        const stack = [];

        let cur = root;

  

        while (cur || stack.length) {

            while (cur) {

                stack.push(cur);

                cur = cur.left;

            }

  

            cur = stack.pop();

            res.push(cur.val);

            cur = cur.right;

        }

  

        return res;

}


function recursiveDFS(root) {
	const res = [];

	const inorder = (node) => {
		if (!node) {
			return;
		}
		
		inorder(node.left);
		res.push(node.val);
		inorder(node.right);
	}
	
	inorder(root);
	
	return res;
}
```