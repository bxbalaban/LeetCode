

# Approach
we create two int named h(horizontal) and v(vertical). Every time we come across L or R we change v. Every time we come across U and D we change h. If at the end the values equals to 0 it means we are back at where we began.

# Complexity
- Time complexity:
 $$O(n)$$ -->n


# Code
```
class Solution {
    public boolean judgeCircle(String moves) {
        char[] m = moves.toCharArray();
        int h=0;
        int v=0;

        for(int i=0; i<m.length; i++){
            if(m[i]=='U') h++;
            if(m[i]=='D') h--;
            if(m[i]=='L') v++;
            if(m[i]=='R') v--;
        }
        
        return (h==0&&v==0);
    }
}
```