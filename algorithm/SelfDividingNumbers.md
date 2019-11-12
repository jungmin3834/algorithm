# algorithm
# selfDividingNumbers

##문제 링크 
##https://leetcode.com/problems/self-dividing-numbers/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/SelfDividingNumbers.png){: width="100%" height="100%"}

```cpp
vector<int> selfDividingNumbers(int left, int right) {
	vector<int> res = vector<int>();
	for (int i = left; i < right + 1; i++)
	{
		if (i % 10 == 0)
			continue;
		string str = to_string(i);
		res.push_back(i);
		for (int j = 0; j < str.size(); j++)
		{
			if (str[j] == '0' || i % (str[j] - '0') != 0)
			{	
				res.pop_back();
				break;
			}
		}
	}
	return res;
}
```