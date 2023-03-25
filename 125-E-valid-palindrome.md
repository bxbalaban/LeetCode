# Approach
Using StringBuilder and charAt() function we simply lower every letter by ascii values. Then reverse the string and check if equal.

# Complexity
- Time complexity:
 $$O(n)$$ n


# Code
```
class Solution {
    public boolean isPalindrome(String s) {
        StringBuilder sb = new StringBuilder();
        char[] ss = s.toCharArray();
        for(int i=0;i<s.length();i++){
            if(ss[i]<91 && ss[i]>64)
            sb.append((char)(ss[i]+32));
            if(ss[i]<123 && ss[i]>96)
            sb.append(ss[i]);
        }
        String reverse = sb.toString();
        return reverse.equals(sb.reverse().toString());
    }
}

```