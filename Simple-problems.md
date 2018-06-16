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
