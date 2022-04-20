## Data Structures

To better write programs that are flexible we need to use suitable data-structures. Each data structure solves a particular problem for example list/arrays are very good when we want to justa access values but are not efficient for delete and insert operations in general, so if we were writing a program that had to do a lot more deletes and inserts a linked-lists for example would be better than an array. 

### Linked Lists

A linked list is a linear data structure where each element in the list is contained in what is called a `Node`. A node contains the actual element and a link (reference or pointer) to the next element on the list.

- The first Node in the list is called the HEAD(start) while the last node is called the TAIL(end)
- Everyone Node in the list has link to the next Node EXCEPT the tail  node. That is how we able to tell when we reach the end of the list. (No link)
- A linked-list may be implement in two ways, the first way is the simply the basic definition of what we call a linked-list with every node having a refernce to the next. That is called a **SINGLY LINKED LIST** on the other hand a we could have a **DOUBLY LINKED LIST** whhere each node holds a reference to BOTH the NEXT and PREVIOUS or preceeding node on the list.

```php
[Item 1 | link] => [Item 2 | link] => [Item 3 | link]  => [Item 4 | link] => [Item 5 | null]
```

### Singly Linked-List Implementation in Python

```python
class Node:
    """
    An object for storing a single node in a linked list

    Attributes:
        data: Data stored in node
        next_node: Reference to next node in linked list
    """

    def __init__(self, data, next_node = None):
        self.data = data
        self.next_node = next_node

    def __repr__(self):
        return "<Node data: %s>" % self.data

class SinglyLinkedList:
    """
    Linear data structure that stores values in nodes. The list maintains a reference to the first node, also called head. Each node points to the next node in the list

    Attributes:
        head: The head node of the list
    """

    def __init__(self):
        self.head = None
        # Maintaining a count attribute allows for len() to be implemented in
        # constant time
        self.__count = 0

    def is_empty(self):
        """
        Determines if the linked list is empty
        Takes O(1) time
        """

        return self.head is None

    def __len__(self):
        """
        Returns the length of the linked list
        Takesn O(1) time
        """

        return self.__count
```

Source : https://teamtreehouse.com/library/introduction-to-data-structures/building-a-linked-list/singly-and-doubly-linked-lists-2
