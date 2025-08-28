---
creation date: 28-08-2025
modification date: Thursday 28th August 2025 08:10:44
---
Rel:
Tags:  #js

There is three phases in even propagation flow
1. Capturing -> event goes down from html tag down to the element, `useCapturing` param of `addEventListener` responsible for triggering the handler during this phase.
2. Targeting -> event reached the target element
3. Bubbling -> event goes up from target element to the top.

`e.stopPropagation()` - stops further propagation of the event. If triggered on capture phase no ca targeting and bubbling happens. But if there are multiple events on the same handler they'll be called.
`e.stopImmediatePropagation()` -` e.stopPropagation()` + the event on the same element won't be triggered.


What the output would be ?
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