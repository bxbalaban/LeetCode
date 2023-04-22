# Approach
What unique here  is Arrays.copy

# Complexity
- Time complexity:
 $$O(n)$$ --> $$n^2$$


# Code
```
class Solution {
    public int countCharacters(String[] words, String chars) {
        int char_arr[] = new int[26];
        int sum = 0;
        for(char c : chars.toCharArray()){
            char_arr[c-'a']++;
        }
        for(String s : words){
            int copy[] = Arrays.copyOf(char_arr,char_arr.length);
            int valid = 0;
            for(char c : s.toCharArray()){
                if(copy[c-'a']>0){
                    valid++;
                    copy[c-'a']--;
                }
            }
            if(valid == s.length()) sum += valid;
        }

        return sum;
    }
}
```