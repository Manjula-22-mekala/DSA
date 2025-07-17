# Question

Given a stack, the task is to sort it such that the top of the stack has the greatest element.


##### Example:
Input:
Stack: 11 2 32 3 41
Output: 41 32 11 3 2


### Naive solution
```python
    def sort_stack_naive(stack):
    # Step 1: Extract all elements into a list
    temp = []
    while stack:
        temp.append(stack.pop())

    # Step 2: Sort the list in descending order
    temp.sort(reverse=True)

    # Step 3: Push back into stack
    for item in temp:
        stack.append(item)

```
# Steps:
# 1. Pop all → O(n)
# 2. Sort list → O(n log n)
# 3. Push back → O(n)
# Therefore Time complexity=O(nlogn)
# Space complexity=O(n)--using extra list


# Optimal Solution


``` python
    def Sorted(self, s):
        # Code here
        if len(s)==0:
            return
        top=s.pop()
        self.Sorted(s)
        self.insertOrder(s,top)
    def insertOrder(self,s,ele):
        if len(s)==0 or s[-1]<ele:
            s.append(ele)
        else:
            temp=s.pop()
            self.insertOrder(s,ele)
            s.append(temp)
            
```
### Time Complexity:O(n²)
### Space Complexity: O(n)--not using any Data structure---got rid off 
