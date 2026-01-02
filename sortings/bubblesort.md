# Question
Do bubble sort


##### Example:
arr = [5, 4, 10, 1, 6, 2]


# Optimal Solution

``` python
    arr=[5,4,10,1,6,2]
    n=len(arr)
    for i in range(n-1):
        flag=0
        for j in range(n-i-1):        
            if arr[j]>arr[j+1]:
                arr[j],arr[j+1]=arr[j+1],arr[j]
                flag=1
        if not flag:
            break
    print(arr)

            
```
### Time Complexity:O(n)--best case,o(n2)--worst/average
### Space Complexity: O(1)
