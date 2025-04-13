Hoisting is a therm which was called to describe the behaviour that variables and function declarations are available before initialization them. Ecmascript specification doesn’t have such a therm, however it’s widely used. What really happens is that during compilation all of the variable and function declarations are marked as a part of some Scope.

There are 3 behaviours which are can be considered as hoisting:

1. Value hoisting - Being able to use a variable value in its scope before the line it is declared(`(async) function, (async) function*`.
2. Declaration hoisting - Being able to reference variable in its scope before the line it’s declared, without throwing `ReferenceError`, but it’s value will be undefined(`var`).
3. The declaration of the variable causes behavior changes in its scope before the line in which it is declared.(`let` and `const`).