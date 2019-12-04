# algorithm
 letter-combinations-of-a-phone-number

## 문제 링크
## https://leetcode.com/problems/letter-combinations-of-a-phone-number/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/letter-combinations-of-a-phone-number.png)


# 코드 리뷰

```cpp
class Solution {
public:
	vector<string> resstring = vector<string>();
	void letterCombination(vector<vector<int>> maplist, string digits, string res, int idx)
	{
		int num = digits[idx++] - '0';
		int size = digits.size();
		for (int i = 0; i < maplist[num].size(); i++)
		{
			string temp = res;
			temp.push_back(maplist[num][i]);

			if (idx == size)
				resstring.push_back(temp);
			else
				letterCombination(maplist, digits, temp, idx);
		}
	}

	vector<string> letterCombinations(string digits) {
		if (digits == "")
			return resstring;

		char ch = 'a';
		vector<vector<int>> veclist = vector<vector<int>>(10);
		for (int i = 2; i < 10; i++)
		{
			for (int j = 0; j < 3; j++)
				veclist[i].push_back(ch++);
			if (i == 7 || i == 9)
				veclist[i].push_back(ch++);
		}

		letterCombination(veclist, digits, "", 0);

		return resstring;
	}
};
```