# Intuition
StringBuilder for not creating bigger space complexity while adding new chars to the string. But we have found a better creation of String clas by giving a char array and the bounds.

# Approach
We have an array at the length of our given string s. Then we create a v,rtual stack with char array. If current char is a match with what is on top of the array we are pushing it by declining index i and adding the new value on top. If not we are increment the i value by 1 meaning we are at the next stack position.

# Complexity
- Time complexity:
$$O(n)$$ --> n 

- Space complexity:
$$O(n)$$ --> n

# Code
```
class Solution {
    public String removeDuplicates(String s) {
        char stack[] = new char[s.length()];
        int i = 0;
        for(int j=0;j<s.length();j++){
            char curr = s.charAt(j);
            if(i>0 && stack[i-1] == curr){ // if the value on top of the stack is equal to the next one 
                i-=1;
            }
            else{
                stack[i] = curr;
                i+=1;
            }
        }
        return new String(stack,0,i);
    }
    /**public String removeDuplicates(String s) {
        boolean check[] = new boolean[27];
        StringBuilder sb = new StringBuilder();
        for(char c : s.toCharArray()){
            int index = c-'a';
            if(check[index]){
                check[index] = false;
                int here = sb.indexOf(c+"");
                sb.delete(here,here+1);
            }
            else{
                check[index]=true;
                sb.append(c+"");
            } 
        }
        return sb.toString();
    } */
}
```