### Pattern: Two Pointers / Remove Duplicates
```python
def removeDuplicates(self, nums: List[int]) -> int:
        low=0
        high=1
        k=1
        while high!=len(nums):
            if nums[high]!=nums[low]:
                low+=1
                nums[low]=nums[high]
                high+=1
                k+=1
            else:
                high+=1
        return k
```
```python
def removeDuplicates(self, nums: List[int]) -> int:
        idx: int = 0
        for i in range(len(nums)):

            if nums[idx] < nums[i]:
                idx+=1
                nums[idx] = nums[i]

        return idx+1
```
##### Problem Link: https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/
##### Time Complexity: O(N)
##### Space Complexity: O(1)

---

```python
def removeDuplicates(self, nums: List[int]) -> int:
        low=0
        high=1
        c=1
        k=1
        while high!=len(nums):
            if nums[low]!=nums[high]:
                low+=1
                nums[low]=nums[high]
                high+=1
                if c>=2:
                    c=1
                k+=1
            elif nums[low]==nums[high] and c==1:
                low+=1
                nums[low]=nums[high]
                high+=1
                c+=1
                k+=1
            elif nums[low]==nums[high] and c>=2:
                high+=1
        return k
```
##### Problem Link: https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
