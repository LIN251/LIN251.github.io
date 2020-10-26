---
Title: Add Two Numbers

Date: 2020-10-24

Author: Linz

---

## Reverse Integer

![](https://i.loli.net/2020/10/26/hMOeIp4dvU8LkEu.png)

#### Idea 1

1. Change int to string.

2. Reverse the string -> list[<start>:<stop>:<step>] therefore **str_num[::-1]** means start form 0 index and end on 0 index, each step is -1 which is reverse steps.

3. Convert string to int.

4. Check out of bound.


```python


def reverse(x):
            if x >= 0:
                str_num = str(x)
                str_num = str_num[::-1]
                int_num = int(str_num)
            else:
                str_num = str(x)
                str_num = str_num[:0:-1]
                str_num = "-" + str_num
                int_num = int(str_num)
            if (int_num >= 2147483647 or int_num <= -2147483648):
                return 0
            else:
                return int_num


if __name__ == '__main__':
    res2 = reverse(2147483649)
    print(res2)


```

![](https://i.loli.net/2020/10/26/q62KdfrLobzu91R.png)