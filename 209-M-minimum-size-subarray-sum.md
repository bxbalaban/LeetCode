# Intuition
Sort the array and sum of all the bigger elements will probably catches the target or some value bigger than the target.

# Approach
We get the sum until we reach the target or the closest value to the target. Then with the inner while loop we check whether we decrement the sum by the left value and then adding a new right value will effect the ultimate result.

# Code
```
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
       int sum = 0;
       int left = 0;
       int result = Integer.MAX_VALUE;

       for(int i=0;i<nums.length;i++){
           sum += nums[i];
           while(sum >= target){
               result = Math.min(result, i+1-left);
               sum -= nums[left];
               left++;
           }
       }
       return (result != Integer.MAX_VALUE) ? result : 0;
    }
    /**public int minSubArrayLen(int target, int[] nums) {
        int count = 0;
        int sum = 0;
        Arrays.sort(nums);
        
        for(int i=nums.length-1;i>=0;i--){
            sum += nums[i];
            count++;
            System.out.println(sum);
            if(sum >= target) return count;
        }
        
        return (sum >= target) ? count : 0;
    } */
}
```