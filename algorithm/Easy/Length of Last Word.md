# algorithm
58. Length of Last Word

##문제 링크
##https://leetcode.com/problems/length-of-last-word/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/length-of-last-word.png)


```cpp
class Solution {
public:
 int lengthOfLastWord(string s) {
	int res = 0;
	for (int i = s.size() - 1; i > -1; i--)
	{
            if(s[i] != ' ')
                res++;
	    else if(res != 0)
                return res;
	}
	return res;
}
};
```
