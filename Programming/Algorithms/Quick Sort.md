---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 19:55:11
---
```
const quickSort = (pairs, start = 0, end = pairs.length - 1) {
	const inPlaceQuickSort = (s, e) => {
		const pivotValue = pairs[e];
		let i = s - 1; //to track the sorted part, === laist idx of sort part
		
		for (j = s; j < e; j++) {
			if (pairs[j] < pivotValue) {
				i++;
				[pairs[i], pairs[j]] = [pairs[j], pairs[i]];
			}
		}
		
		const newPivotidx = i + 1;
		[pairs[newPivotIdx], [pairs[e]] = [pairs[e], pairs[newPivotIdx]];
		return newPivotIds;
	}
	
	if (start < end) { // if its array of 1 element, meaning it's sorted already
		const pivotIdx = inPlaceQuickSort(start, end);
		quickSort(pairs, start, pivot - 1);
		quickSort(pairs, pivot + 1, end);
	}
	
	return pairs;
}
```


Rel: 
Tags:  #algoritms, #sorting
