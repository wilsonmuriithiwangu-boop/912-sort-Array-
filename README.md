# LeetCode 912 - Sort an Array
# Author: Your Name - Student ID

class Solution:
    def sortArray(self, nums):
        # merge sort
        if len(nums) <= 1:
            return nums
        mid = len(nums) // 2
        left = self.sortArray(nums[:mid])
        right = self.sortArray(nums[mid:])
        i=j=0
        res=[]
        while i<len(left) and j<len(right):
            if left[i] <= right[j]:
                res.append(left[i]); i+=1
            else:
                res.append(right[j]); j+=1
        res.extend(left[i:]); res.extend(right[j:])
        return res
