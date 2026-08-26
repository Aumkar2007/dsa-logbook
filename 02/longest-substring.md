### Pattern: Sliding Window / Longest Substring with K Distinct Characters
```python
def longestKSubstr(self, s, k):
        n=len(s)
        low=0
        high=0
        freq={}
        res=-1
        
        for high in range(n):
            freq[s[high]]=freq.get(s[high], 0) + 1     #window expanding
            while len(freq)>k:                         #shrink window if > k unique
                freq[s[low]]-=1
                if freq[s[low]]==0:
                    del freq[s[low]]
                low+=1
            if len(freq) == k:                         # if exactly k unique, check length
                res = max(res, high - low + 1)
        return res
```
##### Problem Link: https://www.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1
##### Time Complexity: O(N)
##### Space Complexity: O(1)
