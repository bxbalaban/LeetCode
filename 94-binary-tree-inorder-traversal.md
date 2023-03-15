# Intuition
Inorder tree is solved mainly by recursions

# Approach
because the tree is in inorder situation we need to consider adding the left values before the right values.

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
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList();
        if(root==null) return result;
        traverseInorder(root,result);
        return result;
    }

    public void traverseInorder(TreeNode node, List<Integer> result){
        if(node==null){
            return;
        }
        
        traverseInorder(node.left,result);
        result.add(node.val);
        traverseInorder(node.right,result);
        
    }
}
```