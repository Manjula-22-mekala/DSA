```python
    class Node: 
    
    def __init__(self, data): 
        self.data = data 
        self.next = None
        
class MyQueue:
    def __init__(self):
        self.start=None
        self.end=None
    #Function to push an element into the queue.
    def push(self, item): 
        self.temp=Node(item)
        if self.start is None:
            self.start=self.end=self.temp
        else:
            self.end.next=self.temp
            self.end=self.temp
         
         #Add code here
    
    #Function to pop front element from the queue.
    def pop(self):
         
         #add code here
         if self.start is None:
             return -1
         self.temp=self.start
         self.start=self.start.next
         return self.temp.data

```