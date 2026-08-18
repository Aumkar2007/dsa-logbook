### Pattern: Two Pointers / Dutch National Flag Problem
```python
def sortColors(self, nums: List[int]) -> None:
        n=len(nums)
        low=0
        mid=0
        high=n-1
        while mid<=high:
            if nums[mid]==0:
                nums[low], nums[mid] = nums[mid], nums[low]
                low+=1
                mid+=1
            elif nums[mid]==1:
                mid+=1
            elif nums[mid]==2:
                nums[high], nums[mid] = nums[mid], nums[high]
                high-=1
```
##### Problem Link: https://leetcode.com/problems/sort-colors/description/
##### Explanation: https://www.youtube.com/watch?v=ljJJcYql6Bc&list=PLbJhGqY-mq47k_WLUtzVjmarUm1EuXPj2&index=8
##### Time Complexity: O(N)
##### Space Complexity: O(1)
