tags: #js #closures

Closure is a function bundled together with references to its surrounding state(which is lexical environment) at the moment of function creation. In other words closure gives you access to outer function scope.



```
`function foo() {`
	`let count = 0;`
	
	`return () => {`
		`count++;`
		`console.log({ count });`
	`}`
`}`

const counter = foo();
counter(); // 2
counter(); // 2

```

```
const cache = {};  
const something = (value) => {  
    if (!cache.current) {  
        cache.current = () => {  
            console.log(value);  
        };  
    }  
    return cache.current;  
};  
  
const first = something('first');  
const second = something('second');  
const third = something('third');  
first(); // logs "first"  
second(); // logs "first"  
third(); // logs "first"
```