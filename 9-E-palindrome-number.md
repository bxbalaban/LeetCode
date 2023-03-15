# Intuition
I was going to use stack and queue but created objects are far more bigger than one simple string. For the sake of space complexity I decided to use string and while loop only

# Approach
Using string and charAt() function we simply compare first and the last chars and iterating

# Complexity
- Time complexity:
 $$O(n)$$ n

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution {
    public boolean isPalindrome(int x) {
        String s= String.valueOf(x);
        int i=0;
        int j=s.length()-1;
        while(i<=j){
            if(s.charAt(i)!=s.charAt(j)) return false;
            i++;
            j--;
        }
        return true;
    }
}
```