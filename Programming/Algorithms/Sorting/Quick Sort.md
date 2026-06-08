---
creation date: 09-05-2026
modification date: Saturday 9th May 2026 20:16:19
learned at: 09-05-2026
last repetaed at: 09-05-2026
---
Rel: 
Tags:  #algoritms, #sorting


```
function quickSort(pairs, start = 0, end = pairs.length - 1) {

        const inPlaceQuickSort = (s, e) => {

            const pivotValue = pairs[e];

            let i = s - 1; //to track the sorted part, === laist idx of sort part

            for (let j = s; j < e; j++) {

                if (pairs[j] < pivotValue) {

                    i++;

                    [pairs[i], pairs[j]] = [pairs[j], pairs[i]];

                }

            }

            const newPivotIdx = i + 1;

            [pairs[newPivotIdx], pairs[e]] = [pairs[e], pairs[newPivotIdx]];

            return newPivotIdx;

        }

        if (start < end) { // if its array of 1 element, meaning it's sorted already

            const pivotIdx = inPlaceQuickSort(start, end);

            quickSort(pairs, start, pivotIdx - 1);

            quickSort(pairs, pivotIdx + 1, end);

        }

        return pairs;

    }
```
