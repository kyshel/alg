

# submit1

``` python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for a in list(range(0,len(nums)-1)):
            for b in list(range(a+1,len(nums))):
                if (nums[a]+nums[b]) == target:
                    print(nums, a,b)
                    return [a,b]
 
          
```


