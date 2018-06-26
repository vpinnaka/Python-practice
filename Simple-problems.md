# Problem 1 [:information_source:](https://www.hackerrank.com/challenges/find-second-maximum-number-in-a-list/editorial)
Find second largest number in a list containing negative numbers
```python
if __name__ == '__main__':
    n = int(input())
    arr = map(int, input().split())
scores = list(arr)
max = max_second = -2147483648
for i in scores:
    if(i > max):
        max_second = max
        max = i
    elif(i > max_second and i != max):
        max_second = i
print(max_second)
```
**test case**
```
4
57 57 -57 57
```
# Problem 2 [:information_source:](https://practice.geeksforgeeks.org/problems/peak-element/1)
Given an array of integers, you need to find the local maxima.
```python
def peakElement(arr, n):
    start = 0
    end = n - 1
    if n == 1:
        return 0
    while(start <= end):
        mid  = (start + end) // 2
        
        """if mid == 0 and arr[mid] >= arr[mid + 1]:
            return mid
        if mid == n - 1 and arr[mid] >= arr[mid -1]:
            return mid
            
        if arr[mid - 1] <= arr[mid] and arr[mid] >= arr[mid + 1]:
            return mid""""
        # optimized code    
        if ((mid == 0 or arr[mid - 1] <= arr[mid]) and (mid == n - 1 or arr[mid + 1] <= arr[mid])):
            return mid
        elif arr[mid] <= arr[mid + 1]:
            start = mid + 1
        elif arr[mid] <= arr[mid - 1]:
            end = mid - 1
    return -1
```
**test case**
```
10, 20, 15, 2, 23, 90, 67

output: 20
```
# Problem 3 [:information_source:](https://practice.geeksforgeeks.org/problems/parenthesis-checker/0)
Parenthesis Checker
```python
def checkIfBalanced(arr):
    stack = []
    for i in range(len(arr)):
        if len(stack) > 0 and getMatchPair(stack[-1]) == arr[i]:
            stack.pop()
        else:
            stack.append(arr[i])
    return (True, False)[len(stack) > 0]

def getMatchPair(bracket):
    return { '(': ')' ,'{': '}' ,'[': ']'}.get(bracket, 'x')
         
if __name__ == '__main__':
    n = int(input())
    for i in range(n):
        arr = input()
        if checkIfBalanced(arr):
            print('balanced')
        else:
            print('not balanced')
```
**test case**
```
Input:
3
{([])}
()
()[]

Output:
balanced
balanced
balanced
```
# Problem 4 [:information_source:](https://practice.geeksforgeeks.org/problems/reverse-a-linked-list/1)
Reversing a linked list
```python
# Python program to reverse a linked list 
# Time Complexity : O(n)
# Space Complexity : O(1)
 
# Node class 
class Node:
 
    # Constructor to initialize the node object
    def __init__(self, data):
        self.data = data
        self.next = None
 
class LinkedList:
 
    # Function to initialize head
    def __init__(self):
        self.head = None
 
    # Function to reverse the linked list
    def reverseList(self):
        if self.head is None:
            return None
        new_head, new_current = None, self.head
        while new_current is not None:
            next_node = new_current.next
            new_current.next = new_head
            new_head = new_current
            new_current = next_node
        self.head = new_head
         
    # Function to insert a new node at the beginning
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        self.head = new_node
 
    # Utility function to print the linked LinkedList
    def printList(self):
        temp = self.head
        while(temp):
            print temp.data,
            temp = temp.next
 
 
# Driver program to test above functions
llist = LinkedList()
llist.push(20)
llist.push(4)
llist.push(15)
llist.push(85)
 
print "Given Linked List"
llist.printList()
llist.reverse()
print "\nReversed Linked List"
llist.printList()
```
**test case**
```
Input:
1
6
1 2 3 4 5 6

Output:
6 5 4 3 2 1
```

