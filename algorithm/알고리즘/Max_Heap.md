# algorithm 
Max_Heap구현

C++ Max_Heap 구현해보기

# 코드

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

void heapCompare(vector<int>& vec ,int idx,int max)
{
	if (idx * 2 <= max&& vec[idx * 2] > vec[idx - 1])
		swap(vec[idx * 2], vec[idx - 1]);
	if (vec[(idx * 2) - 1] > vec[idx - 1])
		swap(vec[(idx * 2) - 1], vec[idx - 1]);
}

void HeapSort(vector<int>& vec)
{
	int idx = vec.size() - 1;
	while (true)
	{
		if (idx == 0)
			break;
		for (int i = (idx + 1) / 2; i > 0; i--)
			heapCompare(vec, i, idx);
		idx--;
		swap(vec[0], vec[idx--]);
	}
}

void MakeHeap(vector<int>& vec)
{
	int idx = vec.size() - 1;
	while (true)
	{
		if (idx == 0)
			break;
		for (int i = (idx + 1) / 2; i > 0; i--)
			heapCompare(vec, i, idx);
		idx--;
	}
}

int HeapDelete(vector<int>& vec)
{
	swap(vec[0], vec[vec.size() - 1]);
	int res = vec.back();
	vec.pop_back();
	int idx = 1;
	while (true)
	{
		if (vec[idx - 1] < vec[(idx * 2)] || vec[idx - 1] < vec[(idx * 2) - 1])
		{
			if (vec[idx - 1] < vec[(idx * 2)])
				swap(vec[idx - 1], vec[(idx * 2)]);
			if (vec[idx - 1] < vec[(idx * 2) - 1])
				swap(vec[idx - 1], vec[(idx * 2) - 1]);
		}
		else
			break;
		idx = idx * 2;
		if (idx * 2 >= vec.size())
		{
			if((idx * 2) -1 < vec.size() && vec[idx -1] < vec[(idx * 2) - 1])
				swap(vec[idx - 1], vec[(idx * 2) - 1]);
			break;
		}
			
	}
	return res;
}

void HeapInsert(vector<int>& vec,int num)
{
	vec.push_back(num);
	int idx = vec.size();
	while (true)
	{
		if (vec[idx - 1] > vec[(idx / 2) - 1])
			swap(vec[idx - 1], vec[(idx / 2) - 1]);
		else
			break;
		idx = (idx / 2);
		if (idx  / 2 <= 0)
			break;
	}
}

int main()
{
	vector<int> vec = vector<int>();
	
	vec = { 1,2,3,4,6};
	
	MakeHeap(vec);

	HeapInsert(vec, 19);
	HeapInsert(vec, 20);
	HeapInsert(vec, 33);
	HeapInsert(vec, 15);
	HeapInsert(vec, 30);

	cout << HeapDelete(vec) << endl;
	cout << HeapDelete(vec) << endl;
	cout << HeapDelete(vec) << endl;
	cout << HeapDelete(vec) << endl;
	cout << HeapDelete(vec) << endl;

	for (int j = 0; j < vec.size(); j++)
		cout << vec[j] << " ";
	cout << endl;

    return 0;
}


```
