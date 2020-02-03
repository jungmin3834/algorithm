# algorithm 
973. K Closest Points to Origin


# 문제 링크  
## https://leetcode.com/problems/k-closest-points-to-origin/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/k-closest-points-to-origin.png)

# 코드

```cpp
class Solution {
public:
    vector<vector<int>> kClosest(vector<vector<int>>& points, int K) {
	vector<int> numlist = vector<int>();
	map<int, vector<vector<int>>> maplist = map<int, vector<vector<int>>>();
	for (int i = 0; i < points.size(); i++)
	{
		int num = points[i][0] * points[i][0] + points[i][1] * points[i][1];
		if (maplist[num].empty() == true)
		{
			maplist[num] = vector<vector<int>>(1, points[i]);
			numlist.push_back(num);
		}
		else
			maplist[num].push_back(points[i]);
		
	}
	sort(numlist.begin(), numlist.end());
	points.clear();

	for (int i = 0; i < numlist.size(); i++)
	{
		vector<vector<int>> temp = maplist[numlist[i]];
		points.insert(points.end(), temp.begin(), temp.end());
		if (K <= points.size())
        {
            temp = vector<vector<int>>(points.begin(), points.begin() + K);
            reverse(temp.begin(),temp.end());
			return temp;
            
        }
	}

	return points;
}
};
```
