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
	const stack = [root];
	let cur = root;
	
	while (cur || stack.length) {
		while (cur.left) {
			stack.push(cur);
			cur = cur.left;
		}
		
		const node = stack.pop();
		if (node.left) stack.push(node.left);
		res.push(node.val);
		if (node.right) stack.push(node.right);	
	}
	
	return res;

}
```