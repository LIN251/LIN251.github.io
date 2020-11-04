---
Title: Roman to Integer

Date: 2020-11-04

Author: Linz

---

## 13. Roman to Integer

![image-20201104134429047](C:\Users\Lin\AppData\Roaming\Typora\typora-user-images\image-20201104134429047.png)

#### Idea 1:

1. Dictionary

2. Backward check

3. Property:

   ```py
   right > left
   CD = 500-100 = D - C
   
   right = left
   II = 1 + 1 = I + I 
   
   right < left
   XI = 10 + 1 = X + I 
   ```

   


#### Code:

```python


def romanToint(romanValue):
    romanDic = {"M":1000, "D":500, "C":100, "L":50, "X":10, "V":5, "I":1}

    previous = romanDic.get(romanValue[-1])
    res = previous
    for x in romanValue[-2::-1]:
        current = romanDic.get(x)

        if previous > current:
            res = res - current
        else:
            res = res + current
        previous = current
    return res

if __name__ == '__main__':
    res = romanToint("LVIII")
    print(res)


```

![](https://i.loli.net/2020/11/05/paOwUG1Mm52AENL.png)

[Reference: How to convert number to roman numerals](https://www.rapidtables.com/convert/number/how-number-to-roman-numerals.html).