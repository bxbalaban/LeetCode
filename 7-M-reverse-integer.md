# Intuition
Strings seemed easy but I knew space complexity would get worse

# Approach
basic math

# Complexity
- Time complexity:
$$O(n)$$ --> n

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution {
    public int reverse(int x) {
       int result=0;
       while(x!=0){
           result=(result*10)+x%10;
           x=x/10;
           if((result<(-214748364) && x!=0) || (result > 214748364 && x!=0))  return 0;
       }
       return result;
    }
}
```