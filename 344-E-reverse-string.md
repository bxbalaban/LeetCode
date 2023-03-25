# Intuition
two pointers

# Approach
there are two pointers starting with right and left side of the array and exchange by iteration

# Complexity
- Time complexity:
$$O(n)$$ --> n


# Code
```
class Solution {
    public void reverseString(char[] s) {
        int right=s.length-1;
        int left=0;
        while(right>=left){
            char temp=s[left];
            s[left]=s[right];
            s[right]=temp;
            left++;
            right--;
        }

    }
}
```