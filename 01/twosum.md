#### Problem Link: https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/
#### Time Complexity: O(N)
#### Space Complexity: O(1)

#### Pattern: Two Pointers / TwoSum
```python
def twoSum(self, numbers: List[int], target: int) -> List[int]:
        n=len(numbers)
        i=0
        j=n-1
        while i<j:
            if numbers[i]+numbers[j]==target:
                return [i+1,j+1]
            elif numbers[i]+numbers[j]>target:
                j-=1
            elif numbers[i]+numbers[j]<target:
                i+=1
```
