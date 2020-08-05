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

Example:

```sh
nums1 = [1,2,3,0,0,0]
nums2 = [2,5,6]
```

```sh
for i in range(3):
  j = i
  print(j)
  while nums1[j] <= nums2[i]:
    j += 1
    print("j",j)
  nums1.insert(j,nums2[i])
  nums1.pop()
```

Resolution: print after every change of the variables to trace

```sh
nums1 = [1,2,3,0,0,0]
nums2 = [2,5,6]

for i in range(3):
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
