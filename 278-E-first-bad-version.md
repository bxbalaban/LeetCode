# Intuition
tried while then binary search method

# Approach

We maintain two pointers left and right that represent the range of versions we are searching. We start with left = 0 and right = n. At each iteration of the while loop, we compute the midpoint mid of the range as (left + right) // 2, and we call the isBadVersion API to check whether version mid is bad or not.

# Complexity
- Time complexity:
$$O(n)$$ logn


# Code

```
/* The isBadVersion API is defined in the parent class VersionControl.
      boolean isBadVersion(int version); */

public class Solution extends VersionControl {
    public int firstBadVersion(int n) {
        //binary search approach
        int low=0;
        int high=n;
    
        while(low<=high){
            int mid=(low+high)/2;
            if(!isBadVersion(mid)){
                low=mid+1;
            }
            else{
                high=mid-1;
            }
        }
        return low;
    }

    public int firstApproach(int n) {
         //constraints 1 <= bad <= n <= 231 - 1 here fails
        int temp=0;
        while(temp<=n){
            if(isBadVersion(temp)) return temp;
            temp++;
        }
        return temp;
    }
}
```