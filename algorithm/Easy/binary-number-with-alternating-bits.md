# algorithm 
693. Binary Number with Alternating Bits





# 문제 링크  
## https://leetcode.com/problems/binary-number-with-alternating-bits/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/binary-number-with-alternating-bits.png)

# 코드

```cpp
class Solution {
public:
    bool hasAlternatingBits(int n) {
    int check = -1 , temp = -1;
	while (n)
	{
		temp = n % 2;
		if (temp == check)
			return false;
		check = temp;
		n >>= 1;
	}
	return true;
    }
};
```
