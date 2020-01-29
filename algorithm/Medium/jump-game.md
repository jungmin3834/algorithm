# algorithm 
55. Jump Game
  
  
  
  
# 문제 링크  
## https://leetcode.com/problems/jump-game/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/jump-game.png)

# 코드

```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
    int size =nums.size();
    for (int jumpCount = 0, i = 0; i < size; i++)
	{
		jumpCount = jumpCount < nums[i] ? nums[i] : jumpCount;
		if (jumpCount-- <= 0)
			return i == size - 1 ? true : false;
	}
	return true;
}
};
```
