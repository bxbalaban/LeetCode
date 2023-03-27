# Intuition
first i went with recurisive approach 

# Approach
we need to explore the right side of the tree first then all we are left with is the left nodes

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
    public static int max;
    public static int curr;

    public int findBottomLeftValue(TreeNode root) {
        Queue<TreeNode> q = new LinkedList();

        q.offer(root);

        while(!q.isEmpty()){
            root=q.poll();
            if(root.right != null){
                q.offer(root.right);
            }
            if(root.left != null){
                q.offer(root.left);
            }
        }

        return root.val;
    }

    public int firstApproach(TreeNode root, int level){
        if(root == null) return -1;

        if(curr == level){
            curr+=1;
            max=root.val;
        }
        firstApproach(root.left,level+1);
        firstApproach(root.right,level+1);

        return max;
    }
}

```