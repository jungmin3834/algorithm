# algorithm 
Birthday Cake Candles



# 문제 링크  
https://www.hackerrank.com/challenges/birthday-cake-candles/problem  

![title](https://github.com/jungmin3834/algorithm/blob/master/image/birthday-cake-candles.png)  

# 코드

```cpp
// Complete the birthdayCakeCandles function below.
int birthdayCakeCandles(vector<int> ar) {
    sort(ar.begin(),ar.end());
    for(int i = ar.size() - 1;i > 0 ;i--)
        if(ar[i] != ar[i - 1])
            return ar.size() - i;
    
    return ar.size();
}

```
