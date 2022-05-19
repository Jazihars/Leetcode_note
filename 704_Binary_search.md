# Leetcode 704题刷题记录
[原始题目链接](https://leetcode.cn/problems/binary-search/)

解答1：
``` python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums) - 1
        while left <= right:
            middle = (left + right) // 2
            if nums[middle] > target:
                right = middle - 1
            elif nums[middle] < target:
                left = middle + 1
            else:
                return middle
        return -1
```

解答2：
``` python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums)
        while left < right:
            middle = (left + right) // 2
            if nums[middle] == target:
                return middle
            elif nums[middle] > target:
                right = middle
            else:
                left = middle + 1
        return -1
```

关于这道题的讲解，参见[704.二分查找](https://github.com/youngyangyang04/leetcode-master/blob/master/problems/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.md)