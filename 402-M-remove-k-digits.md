# Intuition
I tired with slow and fast method but couldn't succeed with the last digit because the length of the string didn't let the last digit to be calculated. Therefore not a good solution.

# Approach
Stack data structure calculates every digit with checking every digit regardless

# Complexity
- Time complexity:
$$O(n)$$ -->n


# Code
```
class Solution {
    public String removeKdigits(String num, int k) {
        int len = num.length();
        if(k==len) return "0";
            
        Stack<Character> stack = new Stack<>();
        StringBuilder sb = new StringBuilder();
        
        int i =0;
        while(i<num.length()){
            //whenever meet a digit which is less than the previous digit, discard the previous one
            while(k>0 && !stack.isEmpty() && stack.peek()>num.charAt(i)){
                stack.pop();
                k--;
            }
            stack.push(num.charAt(i));
            i++;
        }
         // corner case like "1111"
        while(k>0){
            stack.pop();
            k--;            
        }
        while(!stack.isEmpty())
            sb.append(stack.pop());
        sb.reverse();
        
        //remove all the 0 at the head
        while(sb.length()>1 && sb.charAt(0)=='0')
            sb.deleteCharAt(0);
        return sb.toString();
    }
}
```