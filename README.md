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
