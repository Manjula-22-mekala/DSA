# Question

Given an array of integers arr[]. You have to find the Inversion Count of the array. 
Note : Inversion count is the number of pairs of elements (i, j) such that i < j and arr[i] > arr[j]


##### Example:
Input: arr[] = [2, 4, 1, 3, 5]

Output: 3

Explanation: The sequence 2, 4, 1, 3, 5 has three inversions (2, 1), (4, 1), (4, 3).


# Optimal Solution
``` python
    def inversionCount(self, arr):
        # Code Here
        n=len(arr)
        return self.merge_sort(arr,0,n-1)
    def merge(self,arr,low,mid,high):
        temp=[]
        left=low
        right=mid+1
        cnt=0
        while(left<=mid and right<=high):
            if (arr[left]<=arr[right]):
                temp.append(arr[left])
                left+=1
            else:
                temp.append(arr[right])
                cnt+=(mid-left+1)
                right+=1
        while(left<=mid):
            temp.append(arr[left])
            left+=1
        while (right<=high):
            temp.append(arr[right])
            right+=1
        for i in range(low,high+1):
            arr[i]=temp[i-low]
        return cnt
      
    def merge_sort(self,arr,low,high):
        cnt=0
        if low>=high:
            return cnt
        mid=(low+high)//2
        cnt+=self.merge_sort(arr,low,mid)
        cnt+=self.merge_sort(arr,mid+1,high)
        cnt+=self.merge(arr,low,mid,high)
        return cnt        
```
### Time Complexity:O(n log n)
### Space Complexity: O(n)
