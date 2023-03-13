# Intuition
I have decided with going through the array twice while holding the value and comparing in each iteration but time complexity was n2.

# Approach
If you decide to sort the array it will be only one for loop and Array.sort() was my go to.

# Complexity
- Time complexity:
$$O(n)$$ --> n

- Space complexity:


# Code
```
class Solution {
    public boolean containsDuplicate(int[] nums) {
       Arrays.sort(nums);
       for(int i=0;i<nums.length-1;i++){
           if(nums[i]==nums[i+1]){
               return true;
           }
       }
       return false;
    }
}

/*
//my first solution was
boolean flag=false;
        for(int i=0;i<nums.length;i++){
            int hold=nums[i];
            for(int j=0;j<nums.length;j++){
                if(hold==nums[j]&& i!=j){
                    flag=true;
                }
            }
        }
      return flag; 
*/
```