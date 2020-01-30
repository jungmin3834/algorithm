# algorithm
palindrome-number

##문제 링크  

  https://leetcode.com/problems/palindrome-number/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/palindrome-number.png)


#소스 코드

```cpp
class Solution {
public:
   bool isPalindrome(int x) {    
	if(x < 0)
        return false;
       
	string xString = to_string(x);
     int size = xString.length();
	for (int i = 0; i < size /2; i++)
		if (xString[i] != xString[size - 1 - i])
			return false;
	return true;
    }
};
```
