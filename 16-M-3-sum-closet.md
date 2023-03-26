# Intuition
natural instrict is to try to solve it with three individual loops

# Approach
To create less complexity in time I decided to use sort the array and then se two pointers 

# Complexity
- Time complexity:
 $$O(n)$$ --> n^2


# Code
```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int sum = nums[0] + nums[1] + nums[nums.length-1];

        for(int i=0; i<nums.length-2; i++){
            int left=i+1;
            int right=nums.length-1;
            while(left<right){
                int curr = nums[i] + nums[right] + nums[left];
                if(curr>target) right--;
                else left++;

                if(Math.abs(target-curr) < Math.abs(target-sum))
                sum=curr; 
            }
        }
        return sum;
    }
}
```