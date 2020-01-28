# algorithm 
212. Word Search II
  
  
# 문제 링크  
## https://leetcode.com/problems/word-search-ii/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/word-search-ii.png)

# 코드

```cpp
class Solution {
public:
bool checkString(vector<vector<char>> board, string name , int x, int y)
{
	
	if (name.size() == 1)
		return true;
    
    name.pop_back();
    
	board[x][y] = '0';

	if(y + 1 != board[0].size())
		if (board[x][y + 1] == name.back() && checkString(board, name, x, y + 1) == true)
			return true;

	if (y - 1 > -1)
		if (board[x][y - 1] == name.back() && checkString(board, name, x, y - 1) == true)
			return true;

	if (x + 1 != board.size())
		if (board[x + 1][y] == name.back() && checkString(board, name, x + 1, y) == true)
			return true;

	if (x - 1 > -1)
		if (board[x - 1][y] == name.back() && checkString(board, name, x - 1, y) == true)
			return true;

	return false;
}

vector<string> findWords(vector<vector<char>>& board, vector<string>& words) {

	vector<vector<string>> veclist = vector<vector<string>>(26);

	
	for (int i = 0; i < words.size(); i++)
		veclist[words[i].back() - 97].push_back(words[i]);
	
	words.clear();

	for (int i = 0; i < board.size(); i++)
	{
		for (int j = 0; j < board[0].size(); j++)
		{
			if (veclist[board[i][j] - 97].size() != 0)
			{
				for (int z = veclist[board[i][j] - 97].size()- 1; z > -1; z--)
				{
					if (checkString(board, veclist[board[i][j] - 97][z], i, j) == true)
					{
						words.push_back(veclist[board[i][j] - 97][z]);
						veclist[board[i][j] - 97].erase(veclist[board[i][j] - 97].begin() + z);
					}
				}
			}
		}
	}

	return words;
}
};
```
