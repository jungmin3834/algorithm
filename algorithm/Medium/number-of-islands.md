# algorithm 
200. Number of Islands
  
  
  
  
  
# 문제 링크  
## https://leetcode.com/problems/number-of-islands/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/number-of-islands.png)

# 코드

```cpp
class Solution {
public:

void checkIsLand(vector<vector<char>>& grid ,int x,int y)
{
	if (grid[x][y] == '0')
		return;
    
	grid[x][y] = '0';
    
	if (x - 1 >= 0)
		checkIsLand(grid, x - 1, y);

	if (x + 1 < grid.size())
		checkIsLand(grid, x + 1, y);


	if (y - 1 >= 0)
		checkIsLand(grid, x, y - 1);

	if (y + 1 < grid[x].size())
		checkIsLand(grid, x, y + 1);
	
}

int numIslands(vector<vector<char>>& grid) {

	int island = 0;
	for (int i = 0; i < grid.size(); i++)
	{
		 for(int j = 0;j<grid[i].size();j++)
		 {
			 if (grid[i][j] == '1')
			 {
				 island++;
				 checkIsLand(grid,i,j);
			 }
		 }
	}
	return island;
}
};```
