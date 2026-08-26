### Pattern: Sliding Window / Fruits into Baskets 
```python
def totalFruit(self, fruits: List[int]) -> int:
        n=len(fruits)
        low=0
        high=0
        freq={}
        res=0

        for high in range(n):
            freq[fruits[high]]=freq.get(fruits[high], 0) +1

            while len(freq)>2:
                freq[fruits[low]]-=1
                if freq[fruits[low]]==0:
                    del freq[fruits[low]]
                low+=1

            if len(freq)<=2:
                res=max(res,high-low+1)

        return res
```
##### Problem Link: https://leetcode.com/problems/fruit-into-baskets/description/
##### Time Complexity: O(N)
##### Space Complexity: O(1)
