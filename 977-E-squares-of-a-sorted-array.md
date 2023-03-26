# Intuition
two for loops seems the easiest but there is more optimum way

# Approach
we have two pointers starting from the very left and very right. We check which is the bigger and add accordngly to the squared array.

# Complexity
- Time complexity:
$$O(n)$$ --> n


# Code
```
class Solution {
    public int[] sortedSquares(int[] nums) {
        
        int[] sq = new int[nums.length];
        int left=0;
        int right=nums.length-1;

        for(int i=nums.length-1;i>=0;i--){
            if(Math.abs(nums[left])>Math.abs(nums[right])){
                sq[i]=nums[left]*nums[left];
                left++;
            }
            else{
                sq[i]=nums[right]*nums[right];
                right--;
            }
        }
        return sq;

    }
    public int[] firstApproach(int[] nums) {
        int[] sq = new int[nums.length];
        for(int i=0;i<nums.length;i++){
            int squared=nums[i]*nums[i];
            sq[i]=(squared);
            for(int j=0;j<i;j++){
                if(sq[j]>sq[i]){
                    int temp=sq[j];
                    sq[j]=sq[i];
                    sq[i]=temp;
                }
            }
        }
        return sq;
    }
}
```