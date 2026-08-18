### Pattern: Two Pointers / Squaring a Sorted Array
```python
def sortedSquares(self, nums: List[int]) -> List[int]:
        siz=len(nums)
        neg=[]
        pos=[]

        # Separate negatives and positives
        for n in nums:
            if n<0:
                neg.append(n)
            else:
                pos.append(n)
        
        # Case 1:No negative numbers
        if len(neg)==0:
            return [x*x for x in pos]
        
        # Case 2:No positive numbers
        if len(pos)==0:
            res = [x**2 for x in neg]
            res.reverse()
            return res
        
        # Case 3:Both Exist
        neg = [x**2 for x in neg][::-1] 
        pos = [x**2 for x in pos]
        n,m = len(neg), len(pos)
        res=[]

        i=j=0
        while i<n and j<m:
            if neg[i] <= pos[j]:
                res.append(neg[i])
                i+=1
            else:
                res.append(pos[j])
                j+=1
        while i<n:
            res.append(neg[i])
            i+=1
        while j<m:
            res.append(pos[j])
            j+=1
        return res
```
##### Problem Link: https://leetcode.com/problems/squares-of-a-sorted-array/
##### Time Complexity: O(N)
##### Space Complexity: O(N)
