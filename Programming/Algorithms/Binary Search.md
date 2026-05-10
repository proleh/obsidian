---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 21:04:48
learned at: 09-05-2026
last repetaed at: 09-05-2026
---
```
	function iterative_binary_search(nums, target) {
		let l = 0;
		let r = nums.length - 1;
		
		while (l <= r) {
			const mid = l + Math.floor((r - l) / 2);
			
			if (nums[mid] < target) {
				l = mid + 1;
			} else if (nums[mid] > target) {
				r = mid - 1;
			} else {
				return mid; 
			}
		} 
		
		return -1;
	}
	
	recursive_binary_search(nums, target) {
		const helper = (l, r) => {
			if (l > r) {
				return -1;
			}
			
			const mid = l + Math.floor((r - l) / 2);
			if (nums[mid] === target) {
				return mid;
			}
			
			return nums[mid] > target
				? helper(l, mid - 1)
				: helper(mid + 1, r);
		}
		
		
		return helper(0, nums.length - 1)
	}

```

Rel:
Tags: #algoritms
