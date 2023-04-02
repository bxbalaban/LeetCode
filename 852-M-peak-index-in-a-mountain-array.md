# Intuition
linear search

# Approach
binary search

# Complexity
- Time complexity:
$$O(n)$$ --> log(n)


# Code
```
class Solution {
    
    public int peakIndexInMountainArray(int[] arr) {
        int left = 0;
        int right = arr.length;

        while(left < right){
            int mid = (left + right) / 2 ;
            if(arr[mid] < arr[mid+1]) left = mid + 1;
            else right = mid ;
        }

        return left;        
    }
    
    
    /*public int comlexityN(int[] arr) {
        int l = arr.length;
        int max = 0;
        int index = 0;
        for(int i=0 ;i<l;i++){
            if(arr[i] > max){
                index = i;
                max = arr[i];
            }
        }
        return index;
    } */
}
```