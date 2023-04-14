# Intuition

```
public List<String> wordSubsets(String[] words1, String[] words2) {
       List<String> result = new ArrayList();
       
       for(String word : words1){
           boolean flag = true;
           for(String val : words2){
                String wnew = word;
                for(char c : val.toCharArray()){
                    String wanted = c+"";
                    if(wnew.contains(wanted)){
                        wnew = wnew.replaceFirst(wanted,"");
                    }
                    else{
                        flag = false;
                    } 
                }
            }
            if(flag) result.add(word);
        }
        return result; 
    } 
```

# Approach
Better time complexity by a^b. We check the frequency of the letters each time.


# Code
```
class Solution {
    public List<String> wordSubsets(String[] words1, String[] words2) {
       List<String> result = new ArrayList();
       int maxfreq[] = new int[26];
       
        for(String word : words2){
            int list[] = freq(word);
            for(int i=0;i<26;i++){
                maxfreq[i] = Math.max(maxfreq[i],list[i]);
            }
        }
        for(String word : words1){
            int list[] = freq(word);
            boolean flag = true;
            for(int i=0;i<26;i++){
                if(maxfreq[i] > list[i]) flag = false;
            }
            if(flag) result.add(word);
        }
        return result; 
    }
    public int[] freq(String S){
        int result[] = new int[26];
        for(char c : S.toCharArray()){
            result[c-'a']++;
        }
        return result;
    }
    
}
```