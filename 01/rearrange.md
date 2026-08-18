#### Pattern: Two Pointers / Rearrange 0 and 1
```python
def segregate0and1(self, arr):
        z=0
        for i in arr:
            if i==0:
                z+=1
        for i in range(z):
            arr[i]=0
        for i in range(z,len(arr)):
            arr[i]=1
        return arr
```
##### Problem Link: https://www.geeksforgeeks.org/problems/segregate-0s-and-1s5106/1
##### Time Complexity: O(N)
##### Space Complexity: O(1)
