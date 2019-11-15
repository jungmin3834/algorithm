# algorithm 
SingleNumber  
  
  
  
  
  
# 문제 링크  
## https://leetcode.com/problems/single-number/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/SingleNumber.png)

# 코드

```cpp
class Solution {
 public:
    int singleNumber(vector<int>& nums) {
        int num = 0;
        for (int i = 0; i < nums.size(); ++i) 
            num ^= nums[i];
        return num;
    }
};
```
