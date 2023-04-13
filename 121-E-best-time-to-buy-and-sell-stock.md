# Intuition
Using two pointers left and right and checking each element if it is the max or the min while left < right

# Approach
max is the prices[i]-min and min is Integer.MAX_VALUE. If your max is bigger than before it means you found the right one.

# Complexity
- Time complexity: $$O(n)$$ --> n



# Code
```
class Solution {
    public int maxProfit(int[] prices) {

        int max = 0;
        int min = Integer.MAX_VALUE;

        for(int i=0; i<prices.length; i++){
            if(min > prices[i]){
                min = prices[i];
            }
            if(prices[i] - min > max){
                max = prices[i] - min;
            }
        }        
        return max;
    }
}
```