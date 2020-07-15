# algorithm 
Simple Text Editor




# 문제 링크    
https://www.hackerrank.com/challenges/simple-text-editor/problem  


![title](https://github.com/jungmin3834/algorithm/blob/master/image/simple-text-editor.png)

# 코드

```cpp


#include <iostream>
#include <vector>
#include <string>
using namespace std;


void append(string& str, vector<string>& history){
    string appendString;
    cin >> appendString;
    str += appendString;
    history.push_back(str);
}

void remove(string& str,vector<string>& history){
    int index = 0;
    cin >> index;
    for(int i = 0;i<index;i++)
        if(str.empty()==false)
            str.pop_back();
    history.push_back(str);
}

void print(string& str){
    int index = 0;
    cin >> index;
    if(index >= 0 && index - 1 < str.size())
        cout << str[index - 1] << endl;
}

void undo(string& str,vector<string>& history){
    if(history.size() != 0)
        history.pop_back();
    if(history.size() == 0)
        str = "";
    else
        str = history.back();
}

int main() {
    
    int count;
    vector<string> history = vector<string>();
    string str = "";
    cin >> count;

   for(int i =0;i<count;i++){
        int commend;
        cin >> commend;
        switch(commend){
            case 1 : append(str,history); break;
            case 2 : remove(str,history); break;
            case 3 : print(str); break;
            case 4 : undo(str,history); break;
        }
   }
    return 0;
}


```
