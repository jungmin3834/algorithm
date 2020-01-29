# algorithm
409. Longest Palindrome

##문제 링크  

##https://leetcode.com/problems/longest-palindrome/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/longest-palindrome.png)


```cpp
class Solution {
public:
     int longestPalindrome(string s) {
        map<int, int> maplist = map<int, int>();
	    int count = 0;
	    for (int i = 0; i < s.length(); i++)
	    {
		    if (++maplist[s[i]] == 2)
		    {
		    	count += 2;
		    	maplist[s[i]] = 0;
		    }
    	}
	  return count != s.length() ? count + 1 : count;
    }
};
```
