# Question
Do quick sort


##### Example:
arr = [5, 4, 10, 1, 6, 2]


# Optimal Solution

``` python
    #Quick sort
    def quicksort(arr,low,high):
        if low<high:
            loc=partition(arr,low,high)
            quicksort(arr,low,loc-1)
            quicksort(arr,loc+1,high)


    def partition(arr,low,high):
        start=low
        end=high
        pivot=arr[low]
        while(start<end):
            while arr[start]<=pivot:
                start+=1
            while arr[end]>pivot:
                end-=1
            if start<end:
                arr[start],arr[end]=arr[end],arr[start]
        arr[low],arr[end]=arr[end],arr[low]
        return end


    arr=[5,4,10,1,6,2]
    quicksort(arr,0,len(arr)-1)
    print(arr)


            
```
### Time Complexity:O(n log n) in other cases,but o(n2) in worst
### Space Complexity: O(1)
