# algorithm 
1317. Convert Integer to the Sum of Two No-Zero Integers

# 문제 링크  
## https://leetcode.com/problems/convert-integer-to-the-sum-of-two-no-zero-integers/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/convert-integer-to-the-sum-of-two-no-zero-integers.png)

# 코드

```cpp
class Solution {
public:
   bool isZero(int a)
    {
	while (true)
	{
	if (a % 10 == 0)
		return true;
	else if (a < 10)
		return false;
	a /= 10;
	}
    }

	vector<int> getNoZeroIntegers(int n) {
		vector<int> res = vector<int>(2, n / 2);
		res[0] * 2 == n ? NULL : res[0]++; //if n/2 * 2  != n  do plus front of index
		while (true)
		{
			if (isZero(res[0]) == false && isZero(res[1]) == false)  //check is there any 0 in integer
				return res;
			 res[0]++,res[1]--;
		}
		return res;
	}

};
```
