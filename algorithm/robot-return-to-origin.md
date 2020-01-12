# algorithm 
49. Group Anagrams
  
  
# 문제 링크  
## https://leetcode.com/problems/robot-return-to-origin/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/robot-return-to-origin.png)

# 코드
x축과 y축의 값을 가지고 초기축인 0,0 으로 되돌아 오는지 아니면 초가되는 값을 가지고 있는지를 판단하게된다.

```cpp
class Solution {
public:
    bool judgeCircle(string moves) {
            int x = 0;
            int y = 0;
            int size = moves.length();
            for(int i =0;i< size; i++)
            {
                switch (moves[i])
                {
                    case 'U': x++; break;
                    case 'D': x--; break;
                    case 'L': y++; break;
                    case 'R': y--; break;
                }
            }
            if (x == 0 && y == 0)
                return true;
            return  false;
    }
};
```
