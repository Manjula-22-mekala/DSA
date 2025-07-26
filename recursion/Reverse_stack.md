# Question

Given a stack, reverse it so that the top element becomes the bottom.


##### Example:
Input: [3, 2, 1, 7, 6] (6 is top)

Output: [6, 7, 1, 2, 3] (6 is now bottom)


### Naive solution
```python
   def reverse_stack_naive(stack):
    temp = []
    # Step 1: Pop all elements into a temp list
    while stack:
        temp.append(stack.pop())

    # Step 2: Push them back from temp to stack
    for item in temp:
        stack.append(item)

```
# Steps:
# 1. Pop all → O(n)
# 2. Push back → O(n)
### Time Complexity:O(n)
### Space Complexity: O(n)


# Optimal Solution


``` python
    def reverse(self,St): 
        #code here
        if len(St)==0:
            return
        temp=St.pop()
        self.reverse(St)
        self.reversing(St,temp)
    def reversing(self,St,item):
        if len(St)==0:
            St.append(item)
        else:
            top=St.pop()
            self.reversing(St,item)
            St.append(top)
            
```
### Time Complexity:O(n²)
### Space Complexity: O(n)--not using any Data structure---got rid off 
