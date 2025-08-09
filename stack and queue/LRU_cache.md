# Question

Design a data structure that follows the constraints of a Least Recently Used (LRU) cache.


##### Example:
Input
["LRUCache", "put", "put", "get", "put", "get", "put", "get", "get", "get"]
[[2], [1, 1], [2, 2], [1], [3, 3], [2], [4, 4], [1], [3], [4]]
Output
[null, null, null, 1, null, -1, null, -1, 3, 4]

# Optimal Solution


``` python
    class Node:
    def __init__(self,key,value):
        self.key=key
        self.value=value
        self.prev=None
        self.next=None

class LRUCache(object):

    def __init__(self, capacity):
        """
        :type capacity: int
        """
        self.capacity=capacity
        self.cache={}


        self.head=Node(0,0)
        self.tail=Node(0,0)
        self.head.next=self.tail
        self.tail.prev=self.head
        

    def get(self, key):
        """
        :type key: int
        :rtype: int
        """
        if key in self.cache:
            node=self.cache[key]
            self.delete(node)
            self.insert(node)
            return node.value
        else:
            return -1
        

    def put(self, key, value):
        """
        :type key: int
        :type value: int
        :rtype: None
        """
        if key in self.cache:
            node=self.cache[key]
            node.value=value
            self.delete(node)
            self.insert(node)
        else:
            if len(self.cache)==self.capacity:
                node=self.tail.prev
                self.cache.pop(node.key)
                self.delete(node)
            newnode=Node(key,value)
            self.cache[key]=newnode
            self.insert(newnode)

    def delete(self,node):
        prev_node=node.prev
        next_node=node.next
        prev_node.next=next_node
        next_node.prev=prev_node
    def insert(self,node):
        currnodeafterhead=self.head.next
        self.head.next=node
        node.next=currnodeafterhead
        node.prev=self.head
        currnodeafterhead.prev=node


```
### Time Complexity:O(1)
### Space Complexity: O(capacity)
