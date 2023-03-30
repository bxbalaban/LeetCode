# Intuition
recursive and iterative
# Approach
get node from stack with pop() and node.right is peek() 

your space complexity here, e.g. $$O(n)$$ -->

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
    
    public void flatten(TreeNode root) {
        if(root == null) return;
        Stack<TreeNode> s = new Stack<TreeNode>();

        s.push(root);
        while(!s.isEmpty()){
            TreeNode temp = s.pop();
            if(temp.right != null){
                s.push(temp.right);
            }
            if(temp.left != null){
                s.push(temp.left);
            }
            if(!s.isEmpty()) temp.right = s.peek();
            temp.left = null;
        }
    }
   
    /* TreeNode prev;
    public void flatten(TreeNode root) {
        prev = null;
        traverse(root);
    }
    public void traverse(TreeNode root){
        if(root == null) return;
        
        System.out.println(""+root.val);
        
        traverse(root.right);
        traverse(root.left);
        
        root.right = prev;
        root.left = null;
        prev = root;
        
    } */
    
}
```