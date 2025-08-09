# Question

esign and implement a data structure for a Least Frequently Used (LFU) cache.


##### Example
Input
["LFUCache", "put", "put", "get", "put", "get", "get", "put", "get", "get", "get"]
[[2], [1, 1], [2, 2], [1], [3, 3], [2], [3], [4, 4], [1], [3], [4]]
Output
[null, null, null, 1, null, -1, 3, null, -1, 3, 4]
# Optimal Solution


``` python
        class Node:
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.freq = 1
        self.prev = None
        self.next = None
class DoublyLinkedList:
    def __init__(self):
        self.head = Node(0, 0)  # dummy head
        self.tail = Node(0, 0)  # dummy tail
        self.head.next = self.tail
        self.tail.prev = self.head

    def insert_at_head(self, node):
        currnodeafterhead=self.head.next
        self.head.next=node
        node.next=currnodeafterhead
        node.prev=self.head
        currnodeafterhead.prev=node

    def remove_node(self, node):
        prev_node=node.prev
        next_node=node.next
        prev_node.next=next_node
        next_node.prev=prev_node

    def remove_last(self):
        if self.is_empty():
            return None
        last = self.tail.prev
        self.remove_node(last)
        return last

    def is_empty(self):
        return self.head.next == self.tail
class LFUCache(object):

    def __init__(self, capacity):
        """
        :type capacity: int
        """
        self.capacity = capacity
        self.size = 0
        self.min_freq = 0
        self.key_table = {}  # key -> Node
        self.freq_table = defaultdict(DoublyLinkedList)  
        

    def get(self, key):
        """
        :type key: int
        :rtype: int
        """
        if key not in self.key_table:
            return -1
        node = self.key_table[key]
        self._update(node)
        return node.value
        

    def put(self, key, value):
        """
        :type key: int
        :type value: int
        :rtype: None
        """
        if self.capacity==0:
            return

        if key in self.key_table:
            node=self.key_table[key]
            node.value=value
            self._update(node)

        else:
            if self.capacity==self.size:
                lfu_list = self.freq_table[self.min_freq]
                node_to_remove = lfu_list.remove_last()
                if node_to_remove:
                    del self.key_table[node_to_remove.key]
                    self.size -= 1
            new_node = Node(key, value)
            self.key_table[key] = new_node
            self.freq_table[1].insert_at_head(new_node)
            self.min_freq = 1
            self.size += 1
    def _update(self, node):
        freq = node.freq
        self.freq_table[freq].remove_node(node)

        if self.freq_table[freq].is_empty():
            del self.freq_table[freq]
            if self.min_freq == freq:
                self.min_freq += 1

        node.freq += 1
        self.freq_table[node.freq].insert_at_head(node)

```
### Time Complexity:O(1)
### Space Complexity: O(capacity)
