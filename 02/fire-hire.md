### Pattern: Sliding Window / Smallest Subarray with a given sum
```python
def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        n=len(nums)
        low=0
        high=0
        if sum(nums)<target:  
            return 0
        else:
            res=len(nums)
        window_sum=0
        while high<n:
            window_sum+=nums[high]   #hiring from rightside
            while window_sum>=target:
                length=high-low+1
                res=min(res,length)
                window_sum-=nums[low]   #firing from left end
                low+=1
            high+=1
        return res
```
##### Problem Link: https://leetcode.com/problems/minimum-size-subarray-sum/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
