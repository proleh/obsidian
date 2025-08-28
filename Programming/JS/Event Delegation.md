---
creation date: 28-08-2025
modification date: Thursday 28th August 2025 08:10:44
---
Rel:
Tags:  #js

There is three phases in even propagation flow
1. Capturing -> event goes down from html tag down to the element, `useCapturing` param of `addEventListener` responsible for triggering the handler during this phase.
2. Targeting
3. Bubbling


What the output wouild be ?
```html
<div class="outer">
  <div class="inner">
    <button>Click me!</button>
  </div>
</div>
outer.addEventListener("click", () => log("A"), true);
outer.addEventListener("click", () => log("B"));
inner.addEventListener("click", () => log("C"), true);
inner.addEventListener("click", (e) => {
  log("D");
  e.stopPropagation();
  log("E");
});
button.addEventListener("click", () => log("F"));
button.addEventListener("click", () => log("G"), true);
```
### Answer

ACGFDE