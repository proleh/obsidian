---
creation date: 28-08-2025
modification date: Thursday 28th August 2025 08:38:57
---
Rel:
Tags: #css


It's and browser algortithm used to calculate the weight of css selectors to determine which should be applied to the element.
Its three-column value - ID, CLASS, TYPE.
- ID - only id selectors -> for each id  +1-0-0.
- CLASS - class, attributes, pseudo-classes -> for each if the values +0-1-0.
- TYPE - type\tag selectors `p` , `div` and pseudo-elements `::before` -> for each +0-0-1.
