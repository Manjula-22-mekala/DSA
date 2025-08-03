# Optimal
``` python
    class MinStack(object):

    def __init__(self):
        self.st=[]
        self.mini=0

    def push(self, val):
        """
        :type val: int
        :rtype: None
        """
        if len(self.st)==0:
            self.st.append(val)
            self.mini=val
        else:
            if val>self.mini:
                self.st.append(val)
            else:
                self.st.append(2*val-self.mini)
                self.mini=val

    def pop(self):
        """
        :rtype: None
        """
        if not self.st:
            return -1
        x=self.st.pop()
        if x<self.mini:
            self.mini=2*self.mini-x
        return x

    def top(self):
        """
        :rtype: int
        """
        if not self.st:
            return -1
        x=self.st[-1]
        if x<self.mini:
            return self.mini
        else:
            return x

        

    def getMin(self):
        """
        :rtype: int
        """
        return self.mini if self.st else -1
        
            
```
### Time Complexity:O(1)
### Space Complexity:O(n)