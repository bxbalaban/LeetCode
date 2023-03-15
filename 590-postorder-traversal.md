# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
1- create a List to return
2- check if the root is null
3- create recursion function by
*write the exit if and don't forget to pass the last value and return
*iterate through the tree by calling recursion
*add the values to the list

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
    public List<Integer> postorder(Node root) {
        List<Integer> result = new ArrayList<>();

        if(root==null) return result;

        traverseTree(root,result);
        
        return result;
    }
    
    public void traverseTree(Node node, List<Integer> result){

        if(node.children==null){
            result.add(node.val);
            return;
        }

        for(Node child: node.children){
            traverseTree(child,result);
        }

        result.add(node.val);
    }
}
```