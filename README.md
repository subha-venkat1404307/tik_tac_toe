# tik_tac_toe
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

# Create nodes
n1 = Node(10)
n2 = Node(20)
n3 = Node(30)

# Connect nodes
n1.next = n2
n2.prev = n1
n2.next = n3
n3.prev = n2

# Define head and tail
head = n1
tail = n3

#  Forward Traversal (Before insertion)
print("Before Insertion at End (Forward):")
temp = head
while temp is not None:
    print(temp.data, end=" → " if temp.next else "")
    temp = temp.next
print("None")

#  Insert node at end
new_node = Node(40)
tail.next = new_node
new_node.prev = tail
tail = new_node  # update tail to the new node

#  Forward Traversal (After insertion)
print("After Insertion at End (Forward):")
temp = head
while temp is not None:
    print(temp.data, end=" → " if temp.next else "")
    temp = temp.next
print("None")

#  Delete at Start
if head is None:
    print("List is empty")
elif head.next is None:
    head = None
    tail = None
else:
    head = head.next
    head.prev = None

#  Forward Traversal (After Deletion at Start)
print("After Deletion at Start (Forward):")
temp = head
while temp is not None:
    print(temp.data, end=" → " if temp.next else "")
    temp = temp.next
print("None")

#  Delete at End
if tail is None:
    print("List is empty")
elif tail.prev is None:
    head = None
    tail = None
else:
    tail = tail.prev
    tail.next = None

#  Forward Traversal (After Deletion at End)
print("After Deletion at End (Forward):")
temp = head
while temp is not None:
    print(temp.data, end=" → " if temp.next else "")
    temp = temp.next
print("None")

#  Backward Traversal (Tail to Head)
print("Backward Traversal:")
temp = tail
while temp is not None:
    print(temp.data, end=" → " if temp.prev else "")
    temp = temp.prev
print("None")

