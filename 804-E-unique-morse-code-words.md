# Approach
Because we are looking for the unique values we are better use hashset here.

# Complexity
- Time complexity:
$$O(n)$$ --> n^2


# Code
```
class Solution {
    public int uniqueMorseRepresentations(String[] words) {
        String MORSE[] = new String[]{".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."};
        
        HashSet<String> h = new HashSet();

        for(String word : words){

            StringBuilder translation = new StringBuilder();

            for(char c : word.toCharArray()){
               translation.append(MORSE[c-'a']);
            }
            
            h.add(translation.toString());
        }

        return h.size();
    }
}
```