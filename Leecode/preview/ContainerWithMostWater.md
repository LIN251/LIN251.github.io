---
Title: Add Two Numbers

Date: 2020-10-29

Author: Linz

---

## 11. Container With Most Water

![](https://i.loli.net/2020/10/29/YPrTjaHF9zmcMbo.png)

#### Idea 1:

1. Area = (index1 - index2) x(min(list[index1], list[index2]))
2. Always record the max area. 
3. Loop from left and right end. Remove the lower integers until the pointer equal or less than 
4. Return the max area founded.

#### Code1:


```python

def maxArea(hightlist):
    leftIndex = 0
    rightIndex = len(hightlist)-1
    area = 0
    while leftIndex<rightIndex:
        area = max(min(hightlist[leftIndex],hightlist[rightIndex])*(rightIndex-leftIndex) ,area)
        if hightlist[leftIndex] < hightlist[rightIndex]:
            leftIndex = leftIndex + 1
        else:
            rightIndex = rightIndex - 1
    return area

if __name__ == '__main__':
    hightlist = [1,8,6,2,5,4,8,3,7]
    s = maxArea(hightlist)
    print(s)


```

![](https://i.loli.net/2020/10/29/sSJICdQgDZHaM4B.png)

