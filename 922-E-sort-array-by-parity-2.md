# Approach
We create a new array and with a for loop we check if the number is odd or even then we add accordingly to our new array. Although it can be done in a way that you can swap the values that are not in place. But complexity can get worse by n^2

# Complexity
- Time complexity:
$$O(n)$$ --> n

# Code
```
class Solution {
    public int[] sortArrayByParityII(int[] nums) {
        int result[] = new int[nums.length];
        int odd = 1;
        int even = 0;
        for(int i=0; i<nums.length; i++){
            if(nums[i]%2 == 0){
                result[even] = nums[i];
                even+=2;
            }
            else{
                result[odd] = nums[i];
                odd+=2;
            }
        }
        return result;
    }
}
```