# Intuition
I tried to count incvalid chars but there were some problems.

# Approach
A sub function for checking the palindrome for every sub string was usefull at this point.

# Complexity
- Time complexity:
$$O(n)$$ --> n

- Space complexity:
 $$O(n)$$ --> 1

# Code
```
class Solution {
    public boolean validPalindrome(String s) {
        int left = 0;
        int right = s.length()-1;

        while(left < right){
            if(s.charAt(left) == s.charAt(right)){
                left++;
                right--;
            }
            else{
                return isPalindrome(s,left+1,right) || isPalindrome(s,left,right-1) ;
            }
        }
        return true;
    }
    public boolean isPalindrome(String s, int left, int right){
        while(left < right){
            if(s.charAt(left) == s.charAt(right)){
                left++;
                right--;
            }
            else return false;
        }
        return true;
    }
}
```