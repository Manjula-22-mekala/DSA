# Question

Given an array of intervals where intervals[i] = [starti, endi], merge all overlapping intervals, and
return an array of the non-overlapping intervals that cover all the intervals in the input.


##### Example:
Input: intervals = [[1,3],[2,6],[8,10],[15,18]]

Output: [[1,6],[8,10],[15,18]]

Explanation: Since intervals [1,3] and [2,6] overlap, merge them into [1,6].



# Optimal Solution


``` python
    def merge(self, intervals):
        ans=[]
        intervals.sort()
        n=len(intervals)
        for i in range(n):
            start,end=intervals[i][0],intervals[i][1]
            if ans and end<=ans[-1][1]:
                continue
            for j in range(i+1,n):
                if  end>=intervals[j][0]:
                    end=max(end,intervals[j][1])
                else:
                    break
            ans.append([start,end])
        return ans
##tc-o(nlogn)+o(n2)
        ans=[]
        intervals.sort()
        n=len(intervals)
        for i in range(n):
            if not ans or ans[-1][1]<intervals[i][0]:
                ans.append(intervals[i])
            else:
                ans[-1][1]=max(ans[-1][1],intervals[i][1])
        return ans
            
```
### Time Complexity:O(n²)
### Space Complexity: O(n) 
