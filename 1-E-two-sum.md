# Intuition
two for loops
Array.sort with two pointers

# Approach
hashmap looks at constant time to find the keys so we are using that

# Complexity
- Time complexity:
 $$O(n)$$ --> n


# Code
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hm = new HashMap<>();

        for(int i=0;i<nums.length;i++){
            int complement = target - nums[i];
            if(hm.containsKey(complement)) return new int[] {hm.get(complement),i};
            else hm.put(nums[i],i);
        }
        throw new IllegalArgumentException("no match found");
    }
}
```