# Intuition
First i created another function called check ant recursively check every node

# Approach
Then i decided to check right and left side of the tree separately

# Complexity
- Time complexity:
$$O(n)$$ -->n


# Code
```
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public boolean isUnivalTree(TreeNode root) {
        boolean left = root.left == null || root.val == root.left.val && isUnivalTree(root.left);
        boolean right = root.right == null || root.val == root.right.val && isUnivalTree(root.right);
        return right && left ;
    }
    /*int val;
    boolean flag;
    public boolean isUnivalTree(TreeNode root) {
        if(root != null) val = root.val;
        flag=true;
        check(root);
        return flag;
    }
    public void check(TreeNode root){
        if(root == null)  return;
        
        if(root.val != val)  flag=false;

        check(root.right);
        check(root.left);
    }*/
}
```