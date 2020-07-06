# algorithm 
Attribute Parser

 
  
  
# 문제 링크  
## https://www.hackerrank.com/challenges/attribute-parser/problem  

![title](https://github.com/jungmin3834/algorithm/blob/master/image/attribute-parser.png)

# 코드

```cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <stack>
#include <map>
using namespace std;

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */


    string s = "";
    int tagSize, commendSize;
    cin >> tagSize;
    cin >> commendSize;
    for (int i = 0; i<=tagSize; i++)
    {
        string s_t = "";
        getline(cin, s_t);
        s += s_t;
    }
    map<string, string> maplist = map<string, string>();
    vector<string> tagNames = vector<string>();
    vector<string> tagAttribute = vector<string>();
    
    for (int i = 0; i < s.size(); i++)
    {
        if (s[i] == '<' && s[i + 1] != '/') {
            string temp = "";
            string tagName = "";
            tagAttribute.clear();
            while (s[++i] != '>') {
                if (s[i] == ' ' || s[i + 1]=='>') {
                    tagAttribute.push_back(temp);
                    temp = "";
                }
                else if(s[i] == '"')
                    continue;
                else
                    temp += s[i];
            }

            tagNames.push_back(tagAttribute.front());

            if (tagAttribute.size() < 2)
                break;

            for (int j = 0; j < tagNames.size(); j++) 
                tagName += tagNames[j] + '.';
            tagName.back() = '~';
            for (int j = 2; j < tagAttribute.size() - 1; j++)
                if (tagAttribute[j] == "=") 
                      maplist[tagName + tagAttribute[j - 1]] = tagAttribute[j + 1];      
        }
        else if (s[i] == '/') {
            tagNames.pop_back();
        }
    }

    for (int i = 0; i < commendSize; i++) {
        string commend = "";
        getline(cin, commend);
        if (maplist[commend] == "")
            cout << "Not Found!" << endl;
        else
            cout << maplist[commend] << endl;
    }
    
    return 0;
}


```
