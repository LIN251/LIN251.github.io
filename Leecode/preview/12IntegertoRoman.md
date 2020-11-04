---
Title: Integer to Roman

Date: 2020-11-04

Author: Linz

---

## 12. Integer to Roman

![](https://i.loli.net/2020/11/05/KetrjSI6NohqbWY.png)

#### Idea 1:

1. Dictionary

2. Use mod and divide

3. String builder = string* number 

   ```py
   str = "abc"
   str = str * 2
   print(str)
   > abcabc
   ```

   


#### Code:

```python


def intToRoman(intValue):
    romanDic = {1000: "M", 900: "CM", 500: "D", 400: "CD", 100: "C", 90: "XC", 50: "L", 40: "XL", 10: "X", 9: "IX",5: "V", 4: "IV", 1: "I"}
    res = ""
    temp = intValue
    for x in romanDic:
        div = int(temp / x)
        temp = temp % x
        if div == 0:
            continue
        else:
            res = res + romanDic.get(x)*div
        if temp == 0:
            return res
    return res

if __name__ == '__main__':
    res = intToRoman(1994)
    print(res)


```

![](https://i.loli.net/2020/11/05/DsETNbwJUmQdeS4.png)

[Reference: How to convert number to roman numerals](https://www.rapidtables.com/convert/number/how-number-to-roman-numerals.html).