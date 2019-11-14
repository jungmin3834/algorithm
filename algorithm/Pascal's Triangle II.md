# algorithm 
Pascal's Triangle II 
  
  
  
  
  
# 문제 링크  
## https://leetcode.com/problems/pascals-triangle-ii/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/pascals-triangle-ii.png)

# 코드

```cpp
class Solution {
public:
  vector<int> getRow(int rowIndex) {
  
	vector<vector<int>> res = vector<vector<int>>();
  
	res.push_back(vector<int>(1, 1));
        res.push_back(vector<int>(2, 1));
      
	for (int i = 2; i< rowIndex + 1; i++)
	{
		vector<int> temp = vector<int>(1,1);

		for (int j = 0; j < res[res.size() - 1].size() -1; j++)
			temp.push_back(res[res.size() - 1][j] + res[res.size() - 1][j + 1]);
        
		temp.push_back(1);
		res.push_back(temp);
	}
      
	 return res[rowIndex];
 }
};
```
