---
Title: Dichotomy

Date: 2020-10-18

Author: Linz

---

## Dichotomy

### Sample Dichotomy

Search number return index.

| Number | 1   | 5   | 10  | 11  | 15  | 18  | 20  | 30  | 50  |
| ------ | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Index  | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |

Time O(logn)

Space O(1)

```python
from array import *

def Dichotomy(number,index,target):
    leftPos = 0
    rightPos = len(number)-1
    while leftPos<=rightPos:
        mid = (leftPos+rightPos)/2
        if number[mid] > target:
            rightPos = mid - 1
        elif number[mid] < target:
            leftPos = mid + 1
        else:
            return index[mid]
    pass

if __name__ == '__main__':
    T = [[1, 5, 10, 11, 15, 18, 20, 30, 50], [0, 1, 2, 3, 4, 5, 6, 7, 8]]
    number = T[0]
    index = T[1]
    res = Dichotomy(number,index,50)
    print(res)
```

Errors and points:

1. List indices must be integers or slices, not float

```python
mid = (leftPos+rightPos)/2  -->  mid = int((leftPos+rightPos)/2)
```

2. Overflow the Size of int

```python
mid = int((leftPos+rightPos)/2)  -->  mid = left + int((right - left) / 2)
```

If we add two ints together which may greater than the size of the int (2^31 - 1).

### Complicated Dichotomy
