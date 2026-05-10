---
creation date: 03-11-2025
modification date: Monday 3rd November 2025 19:51:03
---
Rel:[[Typescript]]
Tags: #js, #ts


Type alias is just a shortcut for a type
Instead of
```
const person: {age: number, name: string} = {
	age: 12,
	name: 'Paul'
}
```

we can write

```
type Person = {
	age: number;
	name: string
}

const person: Person = {
	age: 12,
	name: 'Paul'
}
```