# Intuition
BFS

# Approach
we need to make a level check with basic traversal

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
    public List<Integer> largestValues(TreeNode root) {
        List<Integer> result = new ArrayList<Integer>();
        if(root!=null) result.add(root.val);
        
        return search(root,0,result);
    }
    public List<Integer> search(TreeNode root,int level, List<Integer> list){
        if(root == null) return list;
        if(level == list.size()) list.add(root.val);
        else{
            list.set(level,Math.max(list.get(level),root.val));
        }
        search(root.left,level+1,list);
        search(root.right,level+1,list);
        return list;
    }
}
```