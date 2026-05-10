---
creation date: 03-11-2025
modification date: Monday 3rd November 2025 11:16:11
---
Rel: [[Typescript]]
Tags: #js, #ts


**Type guards** are expressions that let TypeScript determine the type of a variable inside a conditional block.

A **type guard** is any runtime check that guarantees a variable is of a specific type. Once that check passes, TypeScript “narrows” the variable’s type accordingly.

### ✅ Common Type Guards

#### 1. **`typeof` Type Guard**

Used for primitive types (`string`, `number`, `boolean`, etc.).

`function printValue(value: string | number) {   if (typeof value === "string") {     console.log(value.toUpperCase()); // value is string here   } else {     console.log(value.toFixed(2));    // value is number here   } }`

#### 2. **`instanceof` Type Guard**

Used to check if an object is an instance of a specific class.

`class Dog {   bark() { console.log("Woof!"); } }  class Cat {   meow() { console.log("Meow!"); } }  function makeSound(animal: Dog | Cat) {   if (animal instanceof Dog) {     animal.bark(); // animal is Dog   } else {     animal.meow(); // animal is Cat   } }`

#### 3. **`in` Type Guard**

Checks if a property exists in an object.

`type Car = { wheels: number }; type Boat = { sails: number };  function describe(vehicle: Car | Boat) {   if ("wheels" in vehicle) {     console.log("It's a car");   } else {     console.log("It's a boat");   } }`

#### 4. **User-Defined Type Guards**

You can define a **custom type guard function** using a predicate return type:

`function isString(value: unknown): value is string {   return typeof value === "string"; }  function logLength(value: string | number) {   if (isString(value)) {     console.log(value.length); // value is string   } else {     console.log(value.toFixed(2)); // value is number   } }`

---

## 🎯 Type Narrowing

**Type narrowing** happens when TypeScript refines a variable’s type based on control flow analysis (like `if` statements, `switch`, `typeof`, etc.).  
Type guards are the tools used to achieve type narrowing.

Here’s an example of **narrowing** in action:

`function example(value: string | null) {   if (value) {     // TypeScript narrows type to 'string' because null is falsy     console.log(value.toUpperCase());   } else {     // Here value is 'null'     console.log("No value provided");   } }`

Type narrowing can occur automatically in many cases — TypeScript tracks conditions like `===`, `!==`, `instanceof`, `in`, and even discriminated unions.

---

## 🧠 Discriminated Unions Example

TypeScript excels at narrowing **discriminated unions**, where each type has a literal `kind` property:

`type Circle = { kind: "circle"; radius: number }; type Square = { kind: "square"; side: number }; type Shape = Circle | Square;  function area(shape: Shape) {   switch (shape.kind) {     case "circle":       return Math.PI * shape.radius ** 2; // shape is Circle     case "square":       return shape.side ** 2;              // shape is Square   } }`

Here, `switch (shape.kind)` acts as a **type guard**, and TypeScript automatically **narrows** the union type.