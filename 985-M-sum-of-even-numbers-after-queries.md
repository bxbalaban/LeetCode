# Approach
Sum of all the even values gets change by checking the condition

# Complexity
- Time complexity:
$$O(n)$$ --> n


# Code
```
class Solution {
    public int[] sumEvenAfterQueries(int[] nums, int[][] queries) {
        int result[] = new int[queries.length];
        int S = 0;

        for(int i : nums){
            if(i%2 == 0) 
            S += i;
        }

        for(int i=0; i<queries.length; i++ ){
            int val = queries[i][0];
            int index = queries[i][1];

            if(nums[index]%2 == 0) S -= nums[index];
            nums[index] += val;
            if(nums[index]%2 == 0) S += nums[index];
            result[i] = S;
        }


        return result;
    }
}
```