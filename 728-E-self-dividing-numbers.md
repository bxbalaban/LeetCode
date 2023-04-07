# Intuition
Using int to char but no need for another type when you can have all int solution.

# Approach
At first I created another list for every number to check if it is able to divide and not equal to 0. 
At last I found i%(key%10) != 0 to replace the unnecessary ArrayList to check if it is self-dividing.

# Complexity
- Time complexity:
$$O(n)$$ --> n^2


# Code
```
class Solution {
    public List<Integer> selfDividingNumbers(int left, int right) {
        List<Integer> results = new ArrayList();
        for(int i = left; i<=right; i++){
            int key = i;
            for(;key>0; key/=10){
                if(key%10 == 0 || i%(key%10) != 0)  break;
            }
            if(key == 0) results.add(i);
        }
        return results;
    }
    /*  public List<Integer> selfDividingNumbers(int left, int right) {
        List<Integer> results = new ArrayList();
        for(int i = left; i<=right; i++){
            List<Integer> nums = new ArrayList();
            int key = i;
            while(key>1){
                nums.add(key%10);
                key = key/10;
            }
            boolean flag = true;
            for(Integer val : nums){
                if(val == 0 || i%val != 0){
                    flag = false;
                }
            }
            if(flag) results.add(i);
        }
        return results;
    } */
}
```