# Intuition
Recursive with flag stating it is the left leaf.
Recursive without flag value just checking with if condition.

# Approach
DFS with using Stack 



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
    public int sumOfLeftLeaves(TreeNode root) {
       //DFS Solution
       Stack<TreeNode> s = new Stack();
       int sum = 0;
       if(root == null) return sum;
       s.add(root);
       while(!s.isEmpty()){
           TreeNode temp = s.pop();
           if(temp.left != null){
               s.add(temp.left);
               if(temp.left.right == null && temp.left.left == null) sum += temp.left.val;
           }
           if(temp.right != null){
               s.add(temp.right);
           }
       }
       return sum;
    }
    /*public int recursiveSolution(TreeNode root) {
        if(root == null) return 0;
        if(root.right == null && root.left == null) return 0;

        int sum = 0;
        if(root.left != null && root.left.left == null && root.left.right == null){
            sum += root.left.val;
        }
        
        return sum + sumOfLeftLeaves(root.left) + sumOfLeftLeaves(root.right);
    } */
    
    /* 
    public static int sum;
    public int flagSolution(TreeNode root) {
        sum = 0;
        boolean flag = false;
        sum(root,flag);
        return sum;
    }
    public void sum(TreeNode root,boolean flag) {
        if(root == null) return;
        if(root.right != null){
            flag= false;
            sum(root.right,flag);
        }
        if(root.left != null){
            flag = true;
            sum(root.left,flag);
        } 

        if(root.left == null && root.right == null && flag){
            sum += root.val;
        }
    } */

}
```