# algorithm 
1305. All Elements in Two Binary Search Trees



# 문제 링크  
## https://leetcode.com/problems/all-elements-in-two-binary-search-trees/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/all-elements-in-two-binary-search-trees.png)

# 코드

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
void getAllElement(TreeNode * root, vector<int>& res)
{
	if (root == NULL)
		return;
    
	res.push_back(root->val);

	getAllElement(root->left, res);
	getAllElement(root->right, res);
}

vector<int> getAllElements(TreeNode* root1, TreeNode* root2) {
	
	vector<int> res = vector<int>();

	getAllElement(root1, res);
	getAllElement(root2, res);

	sort(res.begin(),res.end());
	return res;
}
};
```
