# LinkedList 
LinkedList written in python

# Codes
```python
class Node:
    def __init__(self, d):
        self.data = d
        self.next = None
        
    def traverse(self): # print all contents in LinkedList
        n = self
        while n != None:
            print(n.data)
            n = n.next
            
    def addToEnd(self, new_data): # add new node with new_data at the end of the LinkedList
        new = Node(new_data)
        n = self
        while n.next != None:
            n = n.next
        n.next = new
        return n
    
    def addToAfterPosition(self, new_data, position):
        new = Node(new_data)
        n = self
        for i in range(position-1):
            if n.next != None:
                n = n.next
            else:
                print("Error: len smaller than position")
                return -1 # error
        
        new.next = n.next
        n.next = new
        return 0 # success
    
    def deleteNode(self, delete_data):
        head = self
        
        if head.data == delete_data:
            head = head.next
            return head
        
        prev = head
        n = head.next
        
        while n!=None:
            if n.data == delete_data:
                prev.next = n.next
                return
            else:
                prev = n
                n = n.next
```

# creating the linkedlist
```python
one = Node(1)
two = Node(2)
three = Node(3)
one.next = two
two.next = three
one.traverse()
```
output:
```
1
2
3
```

# adding a node to the end
```python
one.addToEnd(4)
one.traverse()
```
output:
```
1
2
3
4
```

# adding after position
```python
one.addToAfterPosition(5,2)
one.traverse()
```
output:
```
1
2
5
3
4
```

# deleting node
```python
one.deleteNode(5)
one.traverse()
```
output:
```
1
2
3
4
```
