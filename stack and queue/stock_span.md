
### optimal solution
```python
    class StockSpanner(object):

    def __init__(self):
        self.st=[]
        self.index=-1

    def next(self, price):
        """
        :type price: int
        :rtype: int
        """
        self.index += 1
        # Pop prices from stack that are <= current price
        while self.st and self.st[-1][0] <= price:
            self.st.pop()

        # If stack is empty, all previous prices are <= current price
        if not self.st:
            span = self.index + 1
        else:
            span = self.index - self.st[-1][1]

        self.st.append((price, self.index))
        return span
```

### Time Complexity:O(n)
### Space Complexity: O(n)
