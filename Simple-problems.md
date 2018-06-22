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
        
        if mid == 0 and arr[mid] >= arr[mid + 1]:
            return mid
        if mid == n - 1 and arr[mid] >= arr[mid -1]:
            return mid
            
        if arr[mid - 1] <= arr[mid] and arr[mid] >= arr[mid + 1]:
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

