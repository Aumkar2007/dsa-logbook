### Pattern: Two Pointers / Merge Sorted Array
```python
def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        # Pointers for the ends of valid elements in nums1 and nums2
        i = m - 1
        j = n - 1
        # Pointer for the very last position in nums1
        k = m + n - 1
        
        # Merge from back to front
        while i >= 0 and j >= 0:
            if nums1[i] > nums2[j]:
                nums1[k] = nums1[i]
                i -= 1
            else:
                nums1[k] = nums2[j]
                j -= 1
            k -= 1
            
        # If there are remaining elements in nums2, copy them over.
        # (If elements remain in nums1, they are already in their correct places)
        while j >= 0:
            nums1[k] = nums2[j]
            j -= 1
            k -= 1
```
##### Problem Link: https://leetcode.com/problems/merge-sorted-array/description/
##### Time Complexity: O(N+M)
##### Space Complexity: O(1)

---

```python
def mergeArrays(self, a, b):
        # Pointer at the end of array a
        left = len(a) - 1
        # Pointer at the beginning of array b
        right = 0
        
        # Swap elements if an element in 'a' is larger than an element in 'b'
        while left >= 0 and right < len(b):
            if a[left] > b[right]:
                a[left], b[right] = b[right], a[left]
                left -= 1
                right += 1
            else:
                # If a[left] <= b[right], all elements are in the correct array
                break
        
        # Sort both arrays to restore sorted order within them
        a.sort()
        b.sort()
```
##### Problem Link: https://www.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1
##### Time Complexity: O((N + M)\log(N + M))
##### Space Complexity: O(1)
