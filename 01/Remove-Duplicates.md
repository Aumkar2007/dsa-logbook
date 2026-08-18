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
        idx: int = 0
        for i in range(len(nums)):

            if nums[idx] < nums[i]:
                idx+=1
                nums[idx] = nums[i]

        return idx+1
