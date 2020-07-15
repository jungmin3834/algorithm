# algorithm 
Encryption


# 문제 링크    
https://www.hackerrank.com/challenges/encryption/problem  


![title](https://github.com/jungmin3834/algorithm/blob/master/image/encryption.png)

# 코드

```cpp

#include <bits/stdc++.h>

using namespace std;

// Complete the encryption function below.
string encryption(string s) {


string result="";
int l= s.size();   //input length
int r = (int) floor(sqrt(l));
int c = (int) ceil(sqrt(l));
int plus = r == c ? 0 : 1;
for(int i =0;i<c;i++){
    string temp = "";
    for(int j = i + r + plus; j < s.size();j += r + plus)
        temp.push_back(s[j]);
    result += s[i] + temp + " ";
}

result.pop_back();
return result;

}

int main()
{
    ofstream fout(getenv("OUTPUT_PATH"));

    string s;
    getline(cin, s);

    string result = encryption(s);

    fout << result << "\n";

    fout.close();

    return 0;
}

```
