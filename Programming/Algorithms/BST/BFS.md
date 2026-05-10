---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 20:38:34
learned at: 09-05-2026
last repetaed at: 09-05-2026
---
```
	function bfs(root) {
		if (!root) {
			return [];
		}
		const res = [];
		const q = [root];
		
		let head = 0;
		while (head < q.length) {
			const tail = q.length - 1;
			const level = [];
			
			while (head <= tail){
				const node = q[head];
				level.push(node.val);
				
				if (node.right) q.push(node.right);
				if (node.left) q.push(node.left); 
				
				head++;
			}
			
			if (level.length) {
				res.push(level);
			}
		}

		return res;
	}

```



Rel:
Tags: #algoritms, #bst 
