# Intuition
2 for loops seemed easy but not optimal

# Approach
We created HashMap and hold the keys with values. If the key is seen before the value updated itself. We check at the end if any keys' value is equal to 1.

We sort the array and check iteratively if there is equality in each 2 value or not.

# Complexity
- Time complexity:
 $$O(n)$$ --> n


# Code
```
class Solution {
    public int singleNumber(int[] nums) {
        Arrays.sort(nums);
        for(int i=0; i<nums.length-1; i+=2){
            if(nums[i] != nums[i+1]){
                return nums[i];
            }         
        }
        return  nums[nums.length-1];
    }
     /*public int singleNumber(int[] nums) {
      HashMap<Integer,Integer> map = new HashMap();
      for(int i=0; i<nums.length; i++){
          if(!map.containsKey(nums[i])){
              map.put(nums[i],1);
          }
          else{
              map.put(nums[i], map.get(nums[i])+1);
          }
      }
      for(Map.Entry<Integer,Integer> val : map.entrySet()){
          int key = val.getKey();
          int fq = val.getValue();

          if(fq == 1) return key;
      }
      return -1;
    } */
}
```