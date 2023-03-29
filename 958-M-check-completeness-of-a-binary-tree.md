# Intuition
I wanted to go with revursive but couldn't made it correctly

# Approach
Here you need to traverse by level order in order to successfully check therefore BFS come in handy. In BFS we use Queue data structure. To check the asked conditions:

- Check if you ever come accross with a null value
- Check if you do and got another not null value

This means the very null value you saw must be the last leaf and if not your tree is not complete.

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
    boolean flag;
    public boolean isCompleteTree(TreeNode root) {
        flag = false;
        Queue<TreeNode> q = new LinkedList();
        q.offer(root);
        while(!q.isEmpty()){
            TreeNode curr = q.poll();
            if(curr == null) flag = true;
            else{
                if(flag){
                    return false;
                }
                else{
                    q.offer(curr.left);
                    q.offer(curr.right);
                }
            }
        }
        return true;
    }
}
```