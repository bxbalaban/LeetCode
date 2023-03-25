# Intuition
Stack and char array for checking and looping through 

# Approach
Using stack data structure we are pushing the non '#' chars and if the char is equal to '#' we are popping the last added one therefore creating a simulation for backspace operation only using # .

# Complexity
- Time complexity:
$$O(n)$$ -->n


# Code
```
class Solution {
    public boolean backspaceCompare(String s, String t) {
        char[] ss =s.toCharArray();
        char[] tt =t.toCharArray();
        int i=0;
        Stack<String> stack = new Stack<String>();

        while(i<s.length()){
            
            if(ss[i]!='#'){
                stack.push(ss[i]+"");
            }
            if(ss[i]=='#' && !stack.empty()){
               stack.pop();
            }
            i++;
        }
        s=stack.toString();

        stack.clear();
        i=0;
        while(i<t.length()){
             if(tt[i]!='#'){
                stack.push(tt[i]+"");
            }
            if(tt[i]=='#' && !stack.empty()){
               stack.pop();
            }
            i++;
        }
        t=stack.toString();
        stack.clear();
  
        return s.equals(t);
    }
}


```