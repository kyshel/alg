
 

``` python
# brute  py
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for a in list(range(0,len(nums)-1)):
            for b in list(range(a+1,len(nums))):
                if (nums[a]+nums[b]) == target:
                    print(nums, a,b)
                    return [a,b]
 
          
```

``` cpp
// brute cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int len = nums.size();
        vector<int> out(2);
        for(int i=0;i!=len-1;i++){
            for(int j=i+1;j!=len;j++){
                if(nums[i]+nums[j] == target){cout << i << " " << j << "\n"; out[0] = i; out[1] = j ;return out; }
            }
            
        }
        
        return out;
    }
};
```


``` cpp
// cpp use map
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        map<int,int> m;
        for(int i=0;i< nums.size(); i++){
            if(m.find(target - nums[i]) != m.end()){
                return {i,m[target - nums[i]]};
            }else{
                m[ nums[i]] = i ;
            }
        }
        
        return {0,0};
    }
};
```




