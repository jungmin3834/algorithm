# algorithm 
1281. Subtract the Product and Sum of Digits of an Integer
  
  
  
# 문제 링크  
## https://leetcode.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/subtract-the-product-and-sum-of-digits-of-an-integer.png)

# 코드

```cpp
class Solution {
public:
  int subtractProductAndSum(int n) {
	int mul = 1 , plus = 0;
	while (n)
	{
		mul *= n % 10;
		plus += n % 10;
		n /= 10;
	}

	return mul - plus;
}
};
```
