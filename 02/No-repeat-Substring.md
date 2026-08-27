### Pattern: Sliding Window / No-repeat Substring
```python
def lengthOfLongestSubstring(self, s: str) -> int:
        n=len(s)
        low=0
        high=0
        freq={}
        res=0
        for high in range(n):
            freq[s[high]]=freq.get(s[high], 0)+1
            k=high-low+1
            while len(freq)<k:
                if freq[s[low]] > 1:
                    freq[s[low]] -= 1
                else:
                    del freq[s[low]]
                low+=1
                k=high-low+1
            if len(freq)==k:
                res=max(res,k)
        return res
```
##### Problem Link: https://leetcode.com/problems/longest-substring-without-repeating-characters/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
