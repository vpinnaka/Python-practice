# Important concepts to revise in python
```python
```
### Reading input
To read the following input use python `map()`
```
5
2 3 6 6 5
```
```python
if __name__ == '__main__':
    n = int(input())
    arr = map(int, input().split())
print(list(arr))
```
### List comprehensions [:twisted_rightwards_arrows:](https://www.hackerrank.com/challenges/list-comprehensions/tutorial)

```python
# print all the combinations where coordinates sum(i+j+k) is less than n
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())
print([[i, j, k] for i in range(x + 1) for j in range(y + 1) for k in range(z + 1) if (i + j + k) != n ])    
```
