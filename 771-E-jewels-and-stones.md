# Intuition
two for loops

# Approach
using indexOf function 

# Complexity
- Time complexity:
$$O(n)$$ --> n


# Code
```
class Solution {
    public int numJewelsInStones(String jewels, String stones) {
       int result = 0;
       for(int i=0 ; i<stones.length();i++){
           if(jewels.indexOf(stones.charAt(i))> -1) result++;
       }
       return result;
    }
    /* public int firstApproach(String jewels, String stones) {
        char j[] = jewels.toCharArray();
        char s[] = stones.toCharArray();
        int result = 0;
        for(int i=0 ;i<s.length;i++){
            for(int k=0 ;k<j.length;k++){
                if(s[i] == j[k]) result ++;
            }
        }
        return result;
    } */
}
```