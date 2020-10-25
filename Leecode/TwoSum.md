---
Title: Two Sum

Date: 2020-10-24

Author: Linz

---

## Two Sum

#### Idea 1

1.Record position info

2.Sort

3.Two pointer move from the beginning and the end

4.check the sum. Since the list be sorted, so we can move the pointer depends the sum value

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_index = []
        for index, i in enumerate(nums):
            num_index.append([i, index])
        # using enumerate to record position.
        # create [(3,0),(2,1),(4,2)]
        # sort by value.
        num_index.sort()
        start = 0
        end = len(nums)-1
        while start<end:
            check = num_index[start][0]+ num_index[end][0]
            if check == target:
                return [num_index[start][1],num_index[end][1]]
            elif check<target:
                start = start + 1
            else:
                end = end -1

if __name__ == '__main__':
    res2 = twoSum([3, 2, 4], 6)
    print(res2)

```

#### Python enumerate function

```python

l1 = ["eat","sleep","repeat"]
s1 = "abcd"

# creating enumerate objects
obj1 = enumerate(l1)
obj2 = enumerate(s1)


print list(enumerate(l1))
print list(enumerate(s1,2))

>output
[(0, 'eat'), (1, 'sleep'), (2, 'repeat')]
[(2, 'a'), (3, 'b'), (4, 'c'), (5, 'd')]

```
