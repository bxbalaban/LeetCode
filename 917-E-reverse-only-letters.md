# Intuition
isLetter() function

# Approach
two indices with one while loop

# Complexity
- Time complexity:
 $$O(n)$$ --> n


# Code
```
class Solution {
    public String reverseOnlyLetters(String s) {
        int left = 0;
        int right = s.length()-1;
       
       char ss[] = s.toCharArray();
       while(left < right){
           if(Character.isLetter(ss[left]) && Character.isLetter(ss[right]) ) {
            char temp = ss[left];
            ss[left]= ss[right];
            ss[right]= temp;
            left++;
            right--;
           }
           if(!Character.isLetter(ss[left])) left++;
           if(!Character.isLetter(ss[right])) right--;
           
       }

        return String.valueOf(ss);
    }
   
}
```