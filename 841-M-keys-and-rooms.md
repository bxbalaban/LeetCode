# Intuition
understand the question first

# Approach
We need to create a boolean list for every room to check if visisted to return a value. We have keys in every room to hold these values we create a stack. We visit every room if the keys in the room is visited we do not add them on stack if not we do. We keep doing this until we have no keys in the stack.

# Complexity
- Time complexity:
$$O(n)$$ --> n^2


# Code
```
class Solution {
    public boolean canVisitAllRooms(List<List<Integer>> rooms) {
        boolean[] seen =new boolean[rooms.size()];
        Stack<Integer> keys = new Stack();
        
        seen[0]=true;
        keys.add(0);

        while(!keys.empty()){
            int room = keys.pop();
            for(int key : rooms.get(room)){
                if(!seen[key]){
                    keys.add(key);
                    seen[key]=true;
                }
            }
        }

        for(boolean visited : seen){
            if(!visited) return false;
        }
        return true;
    }
}
```