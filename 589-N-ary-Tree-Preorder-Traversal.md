# Intuition
recursion function is to go here

# Approach
just as postorder solution, here we are using the recursion method. Only difference is the calling order of the recursive function.

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
    public List<Integer> preorder(Node root) {
        List<Integer> result = new ArrayList<>();

        if(root==null) return result;
        preorderTraversal(root,result);
        return result;
    }

    public void preorderTraversal(Node node, List<Integer> result){

        if(node.children==null){
            result.add(node.val);
            return;
        }

        result.add(node.val);
        for(Node child : node.children){
            preorderTraversal(child, result);
        }
    }
}
```