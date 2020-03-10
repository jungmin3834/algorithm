# algorithm 
K번째수

# 문제 링크  
https://programmers.co.kr/learn/courses/30/lessons/42748

![title](https://github.com/jungmin3834/algorithm/blob/master/image/42748.png)
  
# 코드

```cpp
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

vector<int> solution(vector<int> array, vector<vector<int>> commands) {
    vector<int> answer;
    for(int i =0;i<commands.size();i++)
    {
        vector<int> temp = vector<int>(array.begin() + commands[i][0] - 1 , array.begin() + commands[i][1]);
        sort(temp.begin(),temp.end());
        answer.push_back(temp[commands[i][2] - 1]);
    }
    
    return answer;
}
```
