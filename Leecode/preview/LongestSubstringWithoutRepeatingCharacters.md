---
Title: Longest Substring Without Repeating Characters

Date: 2020-10-25

Author: Linz

---

## Longest Substring Without Repeating Characters

#### Idea 1

![](https://i.loli.net/2020/10/26/PoYBjNGxfhvdcyp.png)

```python
def lengthOfLongestSubstring(s):
    charMap = {}
    for i in range(256):
        charMap[i] = -1
    ls = len(s)
    i = max_len = 0
    for j in range(ls):
        a = ord(s[j])
        b = charMap[a]
        if charMap[a] >= i:
            i = charMap[a] + 1
        charMap[a] = j
        max_len = max(max_len, j - i + 1)
    return max_len



if __name__ == '__main__':
    res2 = lengthOfLongestSubstring("ababc")
    print(res2)
```

#### Solution:

1. i -> substring start position.

2. j -> current pointer position.

3. (j - i + 1) -> suitable substring length.

4. charMap[a] -> update the letter position when it appears.

5. max(max_len, j - i + 1) -> compare the new substring length with the old substring length.

6. i = charMap[a] + 1 -> when a start position of a substring needs to be updated. The last appear position "charMap[a]" + 1 will be the next available substring start position.

7. charMap[a] = j -> record apprear position for each letter.
