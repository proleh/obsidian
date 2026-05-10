---
creation date: 03-11-2025
modification date: Monday 3rd November 2025 11:37:42
---
Rel: [[Typescript]]
Tags: #js, #ts

To Create array

```
const arr: number[] = [1, 2, 3, ...., n]
```

To create Tuple: 
```
type Person = [number, strign];
const tupple: Person = [18, 'Oleh']

const tuple2: Persion = ['Oleh', 18] // Error

```

You can also create readonly tuples to disallow changes(pop and push).