# Intuition
This was seemed like a hard one at fist but two for loops can do anything  

# Approach
We need to recognize teh patter first like adding the 1 at first and seperate the first row by its own. Then itirate with an inner loop to add together to create the  current row 

# Complexity
- Time complexity:
$$O(n)$$ n2

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<>(); // we just initialize here
        if(numRows<1 && numRows>30){
            System.out.println("your range was unexceptible");
            return result ;
        }
        
        List<Integer> firstRow= new ArrayList<>();
        firstRow.add(1); // this is special because it only has 1 in it
        result.add(firstRow);

        //we need to create a for loop the size of a triangle so we can add list accordingly, every iteration we add a list of integer
        for(int i=1;i<numRows; i++){
            //we get the previous row
            List<Integer> prevRow= result.get(i-1);

            //we create the current row
            List<Integer> currentRow= new ArrayList<>();

            //we already know the fisrt element is going to be 1 
            currentRow.add(1);

            //we are going to add 1 at the end too so we are moving to inner loop pf the triangle
            for(int j=1;j<i;j++){
                //so we need to add the elements
                currentRow.add(prevRow.get(j-1)+prevRow.get(j));
            }

            //we are adding the 1 at the end
            currentRow.add(1);

            //we have a completed row at this point 
            result.add(currentRow);
        }

        return result;
    }
}
```