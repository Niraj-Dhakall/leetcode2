# 📝 Majority Element

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Date](https://img.shields.io/badge/Date-10--3--2025-blue)
![Array](https://img.shields.io/badge/Array-lightgrey)
![Hash Table](https://img.shields.io/badge/Hash%20Table-lightgrey)
![Divide and Conquer](https://img.shields.io/badge/Divide%20and%20Conquer-lightgrey)
![Sorting](https://img.shields.io/badge/Sorting-lightgrey)
![Counting](https://img.shields.io/badge/Counting-lightgrey)

</div>

---

## 🔗 Problem Link
**[Majority Element on LeetCode](https://leetcode.com/problems/majority-element)**

---

## 📋 Problem Statement

Given an array `nums` of size `n`, return *the majority element*.

The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.

**Example 1:**

**Input:** nums = [3,2,3]
**Output:** 3

```

**Example 2:**

**Input:** nums = [2,2,1,1,1,2,2]
**Output:** 2

```

**Constraints:**

	• `n == nums.length`

	• `1 4`

	• `-109 9`

**Follow-up:** Could you solve the problem in linear time and in `O(1)` space?

---

-======================💡 Solution & Notes =====================-


```python
from collections import defaultdict
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        d = defaultdict(int)
        for x in nums:
            d[x] += 1
        
        for key, val in d.items():
            if val > (len(nums)//2):
                return key  
```
# Approach
simple hashmap with comparison return at the end
## Time Complexity
O(n)

## Space Complexity
O(n) since you have to make a new dict

## Key Insights
- can avoid default dict to save a bit more memory
- Point 2
- Point 3

## Alternative Solutions
idk


---

## 🏷️ Tags
`Array` • `Hash Table` • `Divide and Conquer` • `Sorting` • `Counting`

---

<div align="center">
  <sub>Generated with ❤️ by LeetCode Tracker</sub>
</div>