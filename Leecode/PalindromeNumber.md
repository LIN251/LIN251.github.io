---
Title: Add Two Numbers

Date: 2020-10-24

Author: Linz

---

## 9. Palindrome Number

![image-20201029110521019](C:\Users\Lin\AppData\Roaming\Typora\typora-user-images\image-20201029110521019.png)

#### Idea 1:

1. Change int to string

2. Two pointer point the the index 0 and len(string)

3. loop through the pointer

   ```py
   Condition:
   1. pointer2 <= pointer1
   	True
   ```

4. char1 == char2 -> update the pointer and continue

5. char1 != char2 -> false Palindrome.

#### Code:


```python


def isPalindrome(x):
    if x < 0:
        return False
    string = str(x)
    pointer1 = 0
    pointer2 = len(string)-1
    while pointer1!=pointer2 :
        if pointer2 <= pointer1:
            return True
        char1 = string[pointer1]
        char2 = string[pointer2]
        if char1 == char2:
            pointer1 = pointer1 +1
            pointer2 = pointer2 -1
            continue
        if char1 != char2:
            return False
    return True


if __name__ == '__main__':
    s = isPalindrome(1001)
    print(s)

```

![](https://i.loli.net/2020/10/29/WnMNevVykhD1Rda.png)