# algorithm
# 938. Range Sum of BST

##문제 링크
##https://leetcode.com/problems/range-sum-of-bst/submissions/

![title](https://github.com/jungmin3834/algorithm/blob/master/image/RangeSumofBST.png)
#
#
#
```cpp
 int rangeSumBST(TreeNode* root, int L, int R) {
        
        int sum = 0;
        if(root->val >= L && root->val <= R)
            sum += root->val;
        
        if(root->left != NULL)
            sum += rangeSumBST(root->left,L,R);
        if(root->right != NULL)
            sum += rangeSumBST(root->right,L,R);
        
        return sum;
}
```

```java
 int rangeSumBST(TreeNode root, int L, int R) {
        int sum = 0;
        
        if(root.val >= L && root.val <= R)
            sum += root.val;
        if(root.left != null)
            sum += rangeSumBST(root.left,L,R);
        if(root.right != null)
            sum += rangeSumBST(root.right,L,R);
     
        return sum;
  }
```
