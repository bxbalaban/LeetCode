# Approach
We are traversing the tree and check if the root.val is higher then low and lower then high we add this to the sum and return it at the end

# Complexity
- Time complexity:
 $$O(n)$$ --> n



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
    int max;
    public int rangeSumBST(TreeNode root, int low, int high) {
        max=0;
        traverse(root,low,high);
        return max;
    }
    public void traverse(TreeNode root,int low, int high){
        if(root == null) return;

        if(root.val >= low && root.val <= high){
            max += root.val;
        }
        traverse(root.left,low,high);
        traverse(root.right,low,high);
    
    }
}
```