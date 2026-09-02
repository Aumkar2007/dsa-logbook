### Pattern: Sliding Window / Minimum Size Substring
```python
def minWindow(self, s: str, t: str) -> str:
        n=len(s)
        low=0
        high=0
        freq_s={}
        freq_t={}
        min_len=n
        start=-1
        formed=0
        for i in t:
            freq_t[i]=freq_t.get(i, 0) + 1
        required=len(freq_t)
        for high in range(n):
            freq_s[s[high]]=freq_s.get(s[high], 0) + 1

            if s[high] in freq_t and freq_s[s[high]] == freq_t[s[high]]:
                formed += 1

            while low<=high and formed==required:
                q=high-low+1
                if q<=min_len:
                    start=low
                    min_len=q
                freq_s[s[low]]-=1
                if s[low] in freq_t and freq_s[s[low]] < freq_t[s[low]]:
                    formed -= 1
                low+=1
        return s[start:start+min_len]
```
##### Problem Link: https://leetcode.com/problems/minimum-window-substring/description/?envType=study-plan-v2&envId=top-interview-150
##### Time Complexity: O(N)
##### Space Complexity: O(1)
