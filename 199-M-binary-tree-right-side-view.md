# Intuition
recursive

# Approach
iterative
when we create the queue the first input is the most right which is what we are looking for. To get the value correctly we need to abstract the first right with i == 0 check

# Complexity
- Time complexity:
 $$O(n)$$ --> n^2


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
    public List<Integer> rightSideView(TreeNode root) {
        Queue<TreeNode> q = new LinkedList();
        List<Integer> l = new ArrayList();
        if(root == null) return l;
        q.offer(root);
        while(!q.isEmpty()){
            int size = q.size(); //important here
            for(int i = 0;i < size; i++ ){
                TreeNode temp = q.poll();
                if(i == 0) l.add(temp.val);
                if(temp.right != null) q.offer(temp.right);
                if(temp.left != null) q.offer(temp.left);
            }
        }
        return l;
    }
    
}
```