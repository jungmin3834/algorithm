# algorithm 
432. All O`one Data Structure
  
  
# 문제 링크  
## https://leetcode.com/problems/all-oone-data-structure/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/all-oone-data-structure.JPG)

# 코드

```cpp

class AllOne {
public:
    vector<string> strlist = vector<string>();
	map<string, int> maplist = map<string, int>();
	string maxstr = "";
	string minstr = "";

	AllOne() {
	}


	/** Inserts a new key <Key> with value 1. Or increments an existing key by 1. */
	void inc(string key) {
		if (maplist[key]++ == 0)
			strlist.push_back(key);

		sortMaxMin();
	}


	/** Decrements an existing key by 1. If Key's value is 1, remove it from the data structure. */
	void dec(string key) {
		if (maplist[key] == 0)
			return;

		maplist[key]--;

		if (maplist[key] == 0)
			for (int i = 0; i < strlist.size(); i++)
				if (strlist[i].compare(key) == 0)
				{
					strlist.erase(strlist.begin() + i);
					break;
				}
        
        
		sortMaxMin();
	}

	void sortMaxMin()
	{
		int max = 0;
        minstr = strlist.front();
		int min = maplist[minstr];
		for (int i = 0; i < strlist.size(); i++)
		{
			string str = strlist[i];
			int num = maplist[str];
			if (max < num)
			{
				max = num;
				maxstr = str;
			}
			if (min > num)
			{
				min = num;
				minstr = str;
			}
		}
	}

	/** Returns one of the keys with maximal value. */
	string getMaxKey() {
		return maxstr;
	}

	/** Returns one of the keys with Minimal value. */
	string getMinKey() {
		return minstr;
	}
};
```
