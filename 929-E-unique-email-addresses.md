# Approach
HashSet keeps the unique values. We are using regex and replaceAll function to operate.

# Complexity
- Time complexity:
 $$O(n)$$ --> n


# Code
```
class Solution {
    public int numUniqueEmails(String[] emails) {
        int count = 0;
        HashSet<String> unique = new HashSet(); // hashset only keeps the unique values 

        for(String email : emails){

            String local = email.substring(0, email.indexOf("@"));
            email = email.substring(email.indexOf("@") , email.length());
            String domain = email;                
            local = local.replaceAll("\\+.*", "");
            local = local.replaceAll("\\.*", "") + domain;

            unique.add(local);
        }
        return unique.size();
    }
}
```