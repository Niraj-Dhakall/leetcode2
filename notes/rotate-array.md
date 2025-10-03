# 📝 Rotate Array

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)
![Date](https://img.shields.io/badge/Date-10--3--2025-blue)
![Array](https://img.shields.io/badge/Array-lightgrey)
![Math](https://img.shields.io/badge/Math-lightgrey)
![Two Pointers](https://img.shields.io/badge/Two%20Pointers-lightgrey)

</div>

---

## 🔗 Problem Link
**[Rotate Array on LeetCode](https://leetcode.com/problems/rotate-array)**

---

## 📋 Problem Statement

Given an integer array `nums`, rotate the array to the right by `k` steps, where `k` is non-negative.

**Example 1:**

**Input:** nums = [1,2,3,4,5,6,7], k = 3
**Output:** [5,6,7,1,2,3,4]
**Explanation:**
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]

```

**Example 2:**

**Input:** nums = [-1,-100,3,99], k = 2
**Output:** [3,99,-1,-100]
**Explanation:** 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]

```

**Constraints:**

	• `1 5`

	• `-231 31 - 1`

	• `0 5`

**Follow up:**

	• Try to come up with as many solutions as you can. There are at least **three** different ways to solve this problem.

	• Could you do it in-place with `O(1)` extra space?

---

-======================💡 Solution & Notes =====================-


```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        k = (k % len(nums))
        temp = nums[-k:]
        nums[k:] = nums[:-k]
        nums[:k] = temp


        return nums
        
```
# Approach
Explain your solution approach here...

if you look at the output, k elements from the end is removed and put up to k index at the front.

like [1,2,3,4] [5,6,7]
then it becomes [5,6,7] [1,2,3,4] as the final array.

## Time Complexity
O(n)

## Space Complexity
O(n)

## Key Insights
- using -k to get the end elements and put from k: to up to k from the end (: -k)
- Point 2
- Point 3

## Alternative Solutions
Discuss other approaches...

YOU CAN JUST REVERSE THE WHOLE LIST
REVERSE THE FIRST 3
THEN REVERSE THE REST
HOLY SHIT

1ST REVERSE: [7,6,5,4,3,2,1]
2ND, REVERSE FROM O TO K-1, EX: THE FIRST 3 ELEMNTS: [5,6,7,4,3,2,1]
THEN JUST REVERSE FROM THE 3RD ELEMENT, INDEX K TO THE END.

---

## 🏷️ Tags
`Array` • `Math` • `Two Pointers`

---

<div align="center">
  <sub>Generated with ❤️ by LeetCode Tracker</sub>
</div>