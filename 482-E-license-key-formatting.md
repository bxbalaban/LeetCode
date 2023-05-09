
# Approach
string builder to save up memory space

# Complexity
- Time complexity:
$$O(n)$$ --> $$n$$

# Code
```
class Solution {
    public String licenseKeyFormatting(String s, int k) {
        s = s.toUpperCase();
        s = s.replaceAll("-","");
        StringBuilder result = new StringBuilder(s);
    
        for(int i=s.length()-k;i>0;i=i-k){
            result.insert(i,"-");
        }
        return result.toString();
    }
}
```