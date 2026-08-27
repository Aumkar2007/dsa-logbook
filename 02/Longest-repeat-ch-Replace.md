### Pattern: Sliding Window / Longest Substring with Same Letters after Replacement
```python
def characterReplacement(self, s: str, k: int) -> int:
        n=len(s)
        low=0
        high=0
        res=-1
        freq={}
        for high in range(n):
            freq[s[high]]=freq.get(s[high], 0) + 1
            l=high-low+1
            maxc = max(freq.values())
            diff = l - maxc
            while diff>k:
                freq[s[low]]-=1
                low+=1
                l=high-low+1
                maxc = max(freq.values())
                diff = l - maxc
            l=high-low+1
            res=max(res,l)
        return res
```
##### Problem Link: https://leetcode.com/problems/longest-repeating-character-replacement/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
