# Intuition
It was first get the index of the first charAt(goal_arr[0]) and check the shifted elements but you can have multiple recursion on the chars so getting the index with indexOf is useless.

# Approach
I literally left shifted every char at s and check if it is a match with the goal string. I've used StringBuilder to gain from the space.

# Complexity
- Time complexity:
$$O(n)$$ --> $n


# Code
```
class Solution {
    public boolean rotateString(String s, String goal) {
        if(s.length() != goal.length()) return false;
        
        StringBuilder sb = new StringBuilder();
        sb.append(s);

        for(int i=0;i<s.length();i++){
            if(sb.toString().equals(goal)) return true;
            else{
                String shift = sb.charAt(0)+"";
                sb.deleteCharAt(0);
                sb.append(shift);
            }
        }
        return false;
    }
}
```