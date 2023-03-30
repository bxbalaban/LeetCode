

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
class Pair {
    TreeNode node; 
    int num; 
    Pair(TreeNode _node, int _num) {
        num = _num;
        node = _node; 
    }
}
class Solution {
    int max;
    HashMap<Integer,Integer> left;
    public int widthOfBinaryTree(TreeNode root) {
       max=0;
       left = new HashMap();
       traverse(root,0,0);
       return max;
    }
    public void traverse(TreeNode root, int depth, int position){
        if(root == null) return;
        left.computeIfAbsent(depth, x->position);
        max = Math.max(max, position - left.get(depth) + 1);
        if(root.left != null) traverse(root.left,depth+1, position*2+1);
        if(root.right != null) traverse(root.right, depth+1,position*2+2);
    }
    
    /*public int widthOfBinaryTree(TreeNode root) {
        List<Integer> l = new ArrayList();
        Queue<Pair> q = new LinkedList();
        q.offer(new Pair(root,0));
        int max = 0;

        while(!q.isEmpty()){
            int size = q.size();
            int min = q.peek().num;
            int last = 0; 
            int first = 0;

            for(int i=0;i<size;i++){
                int position = q.peek().num - min;
                if(i == 0) first = position;
                if(i == size-1) last = position;

                TreeNode curr = q.poll().node;

                if(curr.left!=null){                
                    q.offer(new Pair(curr.left,position*2+1));
                }
                if(curr.right!=null){                
                    q.offer(new Pair(curr.right,position*2+2));
                }
            }
            max = Math.max(max, last-first+1);            
        }        
        return max;
    } */
}
```