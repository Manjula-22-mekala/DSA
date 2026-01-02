# Question
Do mergesort


##### Example:
arr = [5, 4, 10, 1, 6, 2]


# Optimal Solution

``` python
    #merge sort

    def mergesort(arr,low,high):
        
        if low<high:
            mid=(low+high)//2
            mergesort(arr,low,mid)
            mergesort(arr,mid+1,high)
            merge(arr,low,mid,high)

    def merge(arr,low,mid,high):
        i=low
        j=mid+1
        b=[]
        while i<=mid and j<=high:
            if arr[i]<=arr[j]:
                b.append(arr[i])
                i+=1
            else:
                b.append(arr[j])
                j+=1

        while j<=high:
                b.append(arr[j])  
                j+=1

        while i<=mid:
                b.append(arr[i])
                i+=1
        arr[low:high + 1] = b 
        


    arr=[5,4,10,1,6,2]
    mergesort(arr,0,len(arr)-1)
    print(arr)




            
```
### Time Complexity:O(n log n) in all cases
### Space Complexity: O(1)
