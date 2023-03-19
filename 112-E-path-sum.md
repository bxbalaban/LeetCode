# Intuition
We need to traverse the tree in a depth-first manner, keeping track of the sum of values along the path from the root to the current node. When we reach a leaf node, we check if the sum is equal to the target sum. If yes, we return true, otherwise, we continue traversing the tree.

# Approach
We define a function hasPathSum that takes the root node of the binary tree and the target sum as input, and returns a boolean value indicating whether there exists a root-to-leaf path with the given sum.

# Complexity
- Time complexity:
 $$O(n)$$ -> n

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
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }
        if (root.val == targetSum && root.left == null && root.right == null) {
            return true;
        }
        return hasPathSum(root.left, targetSum - root.val) || hasPathSum(root.right, targetSum - root.val);
    }    
}
   
```