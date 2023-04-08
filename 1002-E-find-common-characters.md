# Intuition
Hashmap method

# Approach
Just hold 26 sized int array fill it with Integer.max. Then for every letter update your int array. 


# Code
```
class Solution {
    public List<String> commonChars(String[] words) {
        List<String> result = new ArrayList();
        int results[] = new int[26];
        Arrays.fill(results, Integer.MAX_VALUE);

        for(String word : words){
            int chars[] = new int[26];
            for(char letter : word.toCharArray()){
                chars[letter - 'a']++;
            }
            for(int i=0; i<26; i++){
                results[i] = Math.min(chars[i],results[i]);
            }
        }

        for(int i=0; i<26; i++){
            while(results[i] > 0){
                result.add("" + (char)(i + 'a'));
                results[i]--;
            }
        }
        return result;
    }
    /**public List<String> commonChars(String[] words) {
        List<String> results = new ArrayList();
        HashMap<Character,Integer> map = new HashMap();
        int length = words.length;

        for(String word : words){
            char letters[] = word.toCharArray();
            for(char letter : letters){
                if(!map.containsKey(letter)) map.put(letter,1);
                else map.put(letter, map.get(letter)+1);
            }
        }
        for(Map.Entry<Character,Integer> entry : map.entrySet()){
            int val = entry.getValue();
            char letter = entry.getKey();
            
            if(val >= length  && val < length*2) results.add(letter+"");
            if(val == length*2){
                 results.add(letter+""); results.add(letter+"");
            }
        }

        return results;
    } */
}
```