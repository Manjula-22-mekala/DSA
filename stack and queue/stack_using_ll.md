```python
    class MyStack:
    def __init__(self):
        self.top=None

    # class StackNode:

    # # Constructor to initialize a node
    # def __init__(self, data):
    #     self.data = data
    #     self.next = None
        
    #Function to push an integer into the stack.
    def push(self, data):

        # Add code here
        self.temp=StackNode(data)
        self.temp.next=self.top
        self.top=self.temp
        
    #Function to remove an item from top of the stack.
    def pop(self):
        if self.top is None:
            return -1
        # Add code here
        self.temp=self.top
        self.top=self.top.next
        return self.temp.data

```