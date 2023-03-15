# Intuition
Recursion is first thing to comes to mind

# Approach
we need to exchange the left values to the right values without changing the balance. A simple tmp node helps us to exchange values and we call the left side and then right side recursively.

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

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
    public TreeNode invertTree(TreeNode root) {
        if(root==null) return root;
        
        TreeNode tmp;

        tmp=root.right;
        root.right=root.left;
        root.left=tmp;
        
        invertTree(root.left);
        invertTree(root.right);
        
        return root;
    }


}
```