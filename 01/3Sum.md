### Pattern: Two Pointers / 3Sum
```python
def threeSum(self, nums: list[int]) -> list[list[int]]:
        nums.sort()
        n=len(nums)
        i=0
        res=[]
        while i<n-2:
            if i>0 and nums[i]==nums[i-1]:
                i+=1
            else:
                left=i+1
                right=n-1
                sum=(-1)*nums[i]
                while left<right:
                    if nums[left]+nums[right]==sum:
                        res.append([nums[i], nums[left], nums[right]])
                        left+=1
                        right-=1
                        while left<n and nums[left]==nums[left-1]:
                            left+=1
                        while right>=0 and nums[right]==nums[right+1]:
                            right-=1
                    elif nums[left]+nums[right]>sum:
                        right-=1
                    else:
                        left+=1
                i+=1
        return res
```
##### Problem Link: https://leetcode.com/problems/3sum/
##### Time Complexity: O(N^2)
##### Space Complexity: O(1)
