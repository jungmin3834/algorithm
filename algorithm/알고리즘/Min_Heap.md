# algorithm 
Min_Heap구현

C++ Min_Heap 구현해보기

# 코드

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

void HeapSortHelper(vector<int>& heap , int idx , int limit)
{
	if (idx * 2 < limit && heap[idx - 1] > heap[idx * 2])
		swap(heap[idx - 1], heap[idx * 2]);
	if (heap[idx - 1] > heap[(idx * 2) - 1])
		swap(heap[idx - 1], heap[(idx * 2) - 1]);
}

void HeapSort(vector<int>& heap)
{
	int limit = 0;
	while(true)
	{
		if (limit == heap.size() - 1)
			break;

		for (int i =(heap.size() - limit) / 2; i > 0; i--)
			HeapSortHelper(heap, i, heap.size() - limit);

		swap(heap[0], heap[heap.size() - ++limit]);
	}
}

void HeapMake(vector<int>& heap)
{
	int limit = 0;
	while (true)
	{
		if (limit == heap.size() - 1)
			break;
		for (int i = heap.size() / 2; i > 0; i--)
			HeapSortHelper(heap, i, heap.size());
		limit++;
	}
}

void HeapInsert(vector<int>& vec, int num)
{
	vec.push_back(num);
	int idx = vec.size();
	while (true)
	{
		if (vec[(idx / 2) - 1] > vec[idx - 1])
			swap(vec[(idx / 2) - 1] , vec[idx - 1]);
		idx /= 2;
		if (idx == 1)
			break;
	}
}

int HeapPop(vector<int>& vec)
{
	int res = vec.front(), idx = 1;
	swap(vec[0], vec.back());
	vec.pop_back();
	while (true)
	{
		if (idx * 2 >= vec.size())
			break;
		if (vec[idx - 1] > vec[idx * 2])
			swap(vec[idx - 1], vec[idx * 2]);
		if (vec[idx - 1] > vec[(idx * 2) - 1])
			swap(vec[idx - 1], vec[(idx * 2) - 1]);
		idx *= 2;
	}

	return res;
}

int main()
{
	vector<int> heap = vector<int>({7,5,2,6,3,4,1});
	HeapMake(heap);
	HeapInsert(heap,10);
	HeapInsert(heap,0);

	
	for (int i = 0; i < heap.size(); i++)
	cout << heap[i] << " ";

	cout << endl;
	cout << endl << endl;

	cout << HeapPop(heap) << endl;
	cout << HeapPop(heap) << endl;
	cout << HeapPop(heap) << endl;
	cout << HeapPop(heap) << endl;


    return 0;
}


```
