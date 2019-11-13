# algorithm
# selfDividingNumbers

##문제 링크
##https://leetcode.com/problems/sum-of-root-to-leaf-binary-numbers/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/Sum-of-Root-To-Leaf-Binary-Numbers.png)


#초기화 후 
```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
   	int sumRootToLeaf(TreeNode* root ,int num = 0, int sum = 0) 
    {
		if (root == NULL)
			return 0;

		num = (num << 1) + root->val;
        
		if (root->left == NULL && root->right == NULL)
			return sum + num;
        
		return sumRootToLeaf(root->left, num, sum) + sumRootToLeaf(root->right, num, sum);
	}
};
```

#초기화 전 
```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int sum = 0;
	void getTreeNum(TreeNode* root, vector<int> numlist)
	{
		if (root == NULL)
			return;
		numlist.push_back(root->val);
		if (root->left == NULL && root->right == NULL)
		{
			for (int i = 0; i < numlist.size(); i++)
			{
				if (numlist[i] == 1)
				{
					for (int j = 1; j < numlist.size() - i; j++)
						numlist[i] *= 2;
					sum += numlist[i];
				}
			}
			return;
		}
		getTreeNum(root->left, numlist);
		getTreeNum(root->right, numlist);
	}
	int sumRootToLeaf(TreeNode* root) {
        getTreeNum(root,vector<int>());
		return sum;
	}
};
```