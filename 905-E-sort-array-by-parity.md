# Intuition
two pointers

# Approach
we have right and left value as our two pointers. We do not create another array we just iterate the list checking and swapping accordingly.

# Complexity
- Time complexity:$$O(n)$$ --> n


# Code
```
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        int left = 0;
        int right = nums.length - 1;
        int i = 0;

        while(left <= right){
            if(nums[left]%2 != 0){
                if(nums[right]%2 == 0){
                    int temp = nums[left];
                    nums[left] = nums[right];
                    nums[right] = temp;
                    left++;
                    right--;
                }
                else{
                    right--;
                }                
            }
            else{
                left++;
            }
        }
        
        return nums;
    }
}
```