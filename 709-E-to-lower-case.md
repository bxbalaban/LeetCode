# Intuition
CharArray

# Approach
String to charArray
Check every char between 65 and 97 (ascii uppercase)
Add 32 
convert char array to string

# Complexity
- Time complexity:
$$O(n)$$ --> n


# Code
```
class Solution {
    public String toLowerCase(String s) {
        // U=65-90
        // L=97-122
        
        char[] c = s.toCharArray();
        for(int i=0;i<s.length();i++){
            if(c[i]<91 && c[i]>64){
                c[i]+=32;
            }
        }
        return String.valueOf(c);
    }
}
```