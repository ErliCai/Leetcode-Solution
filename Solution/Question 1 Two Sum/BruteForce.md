

# Brute Force Solution

It is obvious that the problem can be solved by a brute force method. So this is what comes into my mind first:

```
class Solution(object):
    def twoSum(self, nums, target):
        for num1 in nums:
            for num2 in nums:
                Index1 = nums.index(num1)
                Index2 = nums.index(num2)
                if (target == num1 + num2) and (Index1 != Index2):
                    return Index1 , Index2
```

But it fails in test cases 22/29 where the input is:  
  6  
[3,3]  

The reason for this problem is that method index() will return the index of the given element in a list. And thus, it will return [0,0] as result. So I tried to avoid using method index() and modified my result as follow: 


```
class Solution(object):
    def twoSum(self, nums, target):
        Index1 =-1
        for num1 in nums:
                Index1 = n1 + 1
                Index2 = -1
                for num2 in nums:
                    Index2 = Index2 + 1 
                    if  (num1 + num2 == target):
                        if Index1 != Index2:
                            return [Index1,Index2]
```

This solution is less straightforwawrd to see through, but it avoid the problem of two same numbers in the list.
