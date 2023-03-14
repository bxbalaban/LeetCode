# Intuition
First solution which comes to mind was to create two for loops and iterate while holding the value and comparing if the sum is equal to the target but the time complexity can be better.

# Approach
We are approaching with two pointers one starts at the fist and the other starts from the last place from the array we are given. It compares the sum by one for loop which is only the size of the array. If the sum is lower than the target we move first pointer +1 and if higher we move last pointer -1 .

# Complexity
- Time complexity:
 $$O(n)$$ --> n

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int[] result= new int[2];
        int pointerFirst=0;
        int pointerLast=(numbers.length-1);

        for(int i=0;i<numbers.length;i++){
            int sum=numbers[pointerFirst]+numbers[pointerLast];
            if(sum==target){
                result[0]=pointerFirst+1;
                result[1]=pointerLast+1;
            }
            else if(sum<target){
                pointerFirst++;
            }
            else{
                pointerLast--;
            }
        }
        return result;
    }
}
```