---
Title: Add Two Numbers

Date: 2020-10-24

Author: Linz

---

## String to Integer (atoi)

![](https://i.loli.net/2020/10/26/s3VXw5LCm9bUq7y.png)

#### Idea 1

1. Remove space.

   ```py
   str = str.replace(' ', '')
   # "   +0 123" ->
   # "+0123"
   
   str = ''.join(sentence.split())
   # "   +0 123" ->
   # "+0123"
   
   str = " ".join(s.split()) 
   # "   +0 123" 
   # "+0 123"
   ```

2. If the string start with +/-. We can re-arrange the string by using str[1::1] to produce a substring from index 1.

3. Check whether each char is a number each.isdigit().

4. Break when we see a "space".

5. Some conditions need to return 0.

   "0000",  "+",  "-",  "-+",  "-0000"

6. Check whether number out of bound. 

   


```python


# "-+12"
#"   +0 123"
#"-   234"
def reverse(s):
    result = ""
    s = " ".join(s.split())
    if s == "":
        return 0
    if s[0] == "-" or s[0] == "+":
        if s[0] == "-":
            result += "-"
        s = s[1::1]

    for each in s:
        if each.isdigit():
            result += each
        elif each == "0":
            continue
        elif each == " ":
            break
        else:
            break
    if result == "" or result == "-":
        return 0
    num = int(result)
    if num >= 2147483647:
        return 2147483647
    elif num <= -2147483648:
        return -2147483648
    else:
        return num


if __name__ == '__main__':
    res2 = reverse("-+12")
    print(res2)


```

![](https://i.loli.net/2020/10/27/O7ZJfEMb6yi9aS1.png)