# algorithm 
844. Backspace String Compare
  
  
## 문제 링크  
## https://leetcode.com/problems/backspace-string-compare/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/backspace-string-compare.JPG)

## 코드

```cpp
class Solution {
public:
string spaceCompare(string S)
{
	string temp = "";
	for (int i = 0; i < S.size(); i++)
	{
		if (S[i] != '#')
			temp.push_back(S[i]);
		else if (temp.empty() == false)
			temp.pop_back();
	}
	return temp;
}

bool backspaceCompare(string S, string T) {
	return spaceCompare(S) == spaceCompare(T) ? 1 : 0;
}
};
```
