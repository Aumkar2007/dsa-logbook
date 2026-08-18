### Pattern: Sliding Window / Maximum Sum Subarray of Size K
```python
def maxSubarraySum(self, arr, k):
        n=len(arr)
        if n < k:    #working for edgecase
         return 0
        low=0        #setting low pointer
        high=k-1     #setting high pointer
        max_sum=0    #answer
        window_sum=sum(arr[:k])   #calculating window sum
        while high<n:
            max_sum=max(max_sum,window_sum)
            low+=1
            high+=1
            if high==n:          #To not get index error
                break
            window_sum=window_sum - arr[low-1] + arr[high]      
        return max_sum
```
##### Problem Link: https://www.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1
##### Time Complexity: O(N)
##### Space Complexity: O(1)
