# Question
Do insertion sort


##### Example:
arr = [5, 4, 10, 1, 6, 2]


# Optimal Solution

``` python
    arr=[5,4,10,1,6,2]
    n=len(arr)
    for i in range(1,n):
        temp=arr[i]
        j=i-1
        while j>=0 and arr[j]>temp:
            arr[j+1]=arr[j]
            j=j-1
        arr[j+1]=temp
    print(arr)

            
```
### Time Complexity:O(n)--best case,o(n2)--worst/average
### Space Complexity: O(1)
