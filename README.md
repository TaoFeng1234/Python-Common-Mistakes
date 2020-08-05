# Python-Common-Mistakes
Some common mistakes I made as a beginner in Python 

## Index and for loop

My goal is to obtain the indexes of all the '1's in a list. 

`List = [1,0,1,1,0,1]
[List.index(x) for x in List if x == 1]`

Output: [0, 0, 0, 0]

The 'List.index(x)' looks for the index for the first '1' in the list. Thus it only returns the index for the first '1' in the list above. 

Fix:
 
`[i for i in range(len(List)) if List[i] == 0]`

output: [1, 4]

## IndexError: list index out of range

Example: Merge Sorted Array (https://leetcode.com/explore/learn/card/fun-with-arrays/525/inserting-items-into-an-array/3253/)

Testcase:
```sh
nums1 = [1,2,3,0,0,0]
m = 3
nums2 = [2,5,6]
n = 3
```

Code:
```sh
for i in range(n):
  j = i
  while nums1[j] <= nums2[i]:
    j += 1
    print("j",j)
  nums1.insert(j,nums2[i])
  nums1.pop()
```
Output: IndexError: list index out of range

How to trouble shoot: print after every change of the variables to trace

```sh
nums1 = [1,2,3,0,0,0]
nums2 = [2,5,6]

for i in range(n):
  j = i
  print(j)
  len = 3
  while nums1[j] <= nums2[i] and j < len :
    j += 1
    print("j",j)
  nums1.insert(j,nums2[i])
  nums1.pop()
  print(nums1)
  len += 1
 ```
Accepted Submission:

```sh
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        len = m
        for i in range(n):
            j = i
            while nums1[j] <= nums2[i] and j < len :
                j += 1
            nums1.insert(j,nums2[i])
            nums1.pop()
            len += 1
```            
