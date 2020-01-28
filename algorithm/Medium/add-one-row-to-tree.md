# algorithm 
623. Add One Row to Tree





# 문제 링크  
## https://leetcode.com/problems/add-one-row-to-tree/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/add-one-row-to-tree.png)

# 코드

```cpp
/**
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
TreeNode* TreeMaker(int v)
{
	return new TreeNode(v);
}

void searchDept(TreeNode* root, int v, int d ,int dept)
{
    if(root == NULL)
        return;
	if (++dept== d)
	{
		TreeNode *tempA = root->left;
		TreeNode *tempB = root->right;
		root->right = TreeMaker(v);
		root->left = TreeMaker(v);
		root->right->right = tempB;
		root->left->left = tempA;
		return;
	}
	searchDept(root->left,v,d,dept);
	searchDept(root->right, v,d, dept);
}


TreeNode* addOneRow(TreeNode* root, int v, int d) {
	
	if (d == 1)
	{
		TreeNode * temp = TreeMaker(v);
		temp->left = root;
		temp->right = NULL;
		return temp;
	}
	else
		searchDept(root, v, d, 1);
	return root;
}
};
```
