### Pattern: Two Pointers / TwoSum
```python
def twoSum(self, numbers: List[int], target: int) -> List[int]:
        n=len(numbers)
        i=0      #One pointer at the start
        j=n-1    #Second Pointer at the end
        while i<j:   #While loop until pointers cross each other
            if numbers[i]+numbers[j]==target:    #Answer
                return [i+1,j+1]
            elif numbers[i]+numbers[j]>target:   #Condition to lower end pointer in sorted array
                j-=1
            elif numbers[i]+numbers[j]<target:   #Condition to increase start pointer in sorted array
                i+=1
```
##### Problem Link: https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
