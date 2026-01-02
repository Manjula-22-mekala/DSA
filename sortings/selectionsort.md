# Question
Do quick sort


##### Example:
arr = [5, 4, 10, 1, 6, 2]


# Optimal Solution

``` python
    #Quick sort
    arr=[5,4,10,1,6,2]
    n=len(arr)
    for i in range(n):
        mini=i
        for j in range(i+1,n):
            if arr[j]<arr[mini]:
                mini=j
        if mini!=i:
            arr[i],arr[mini]=arr[mini],arr[i]
    print(arr)


            
```
### Time Complexity:O(n**2) in all cases
### Space Complexity: O(1)
