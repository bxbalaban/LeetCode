# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
-Sort the array in ascending order.
-Set the low index to the first element of the array and the high index to the last element.
-Set the middle index to the average of the low and high indices.
-If the element at the middle index is the target element, return the middle index.
-If the target element is less than the element at the middle index, set the high index to the middle index – 1.
-If the target element is greater than the element at the middle index, set the low index to the middle index + 1.

*from https://www.geeksforgeeks.org/binary-search/

# Complexity
- Time complexity:
 $$O(n)$$ --> logn


# Code
```
class Solution {
    public int search(int[] nums, int target) {
        return binarySearch(nums,0,nums.length,target);
    }

    public int binarySearch(int[] nums, int low, int high, int target){
        int middle=(high+low)/2;
        
        if(low>high||high<low||middle==nums.length) return -1;

        if(nums[middle]==target) return middle;

        if(nums[middle]>target) return binarySearch(nums,low,middle-1,target);
        if(nums[middle]<target) return binarySearch(nums,middle+1,high,target);

        return -1;

    }
    
}

```