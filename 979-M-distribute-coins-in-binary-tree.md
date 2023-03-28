
# Approach
we traverse the tree. There is a simple math behind it you basically need to sum every node then you need to subtract 1 out of it. 


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
    public static int result;
    public int distributeCoins(TreeNode root) {
        result = 0;
        check(root);
        return result;
    }
    public int check(TreeNode root){
        if(root == null) return 0;

        int left = check(root.left);
        int right = check(root.right);

        result += Math.abs(left) + Math.abs(right);
        
        return root.val + left + right - 1;
    }
    
}
```