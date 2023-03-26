# Approach
two pointers check the max container. 

# Complexity
- Time complexity:
$$O(n)$$ --> n

# Code
```
class Solution {
    public int maxArea(int[] height) {
        int max=0;
        int right= height.length-1;
        int left=0;
        while(right>left){

            int y = Math.min(height[right],height[left]);
            int x = right-left;

            max = Math.max(max,x*y);

            if(height[right]>=height[left]) left++;
            else right--;
        }
        return max;
    }
}
```