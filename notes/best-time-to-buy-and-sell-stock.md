# 📝 Best Time to Buy and Sell Stock

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Date](https://img.shields.io/badge/Date-10--3--2025-blue)
![Array](https://img.shields.io/badge/Array-lightgrey)
![Dynamic Programming](https://img.shields.io/badge/Dynamic%20Programming-lightgrey)

</div>

---

## 🔗 Problem Link
**[Best Time to Buy and Sell Stock on LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock)**

---

## 📋 Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return *the maximum profit you can achieve from this transaction*. If you cannot achieve any profit, return `0`.

**Example 1:**

**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

```

**Example 2:**

**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transactions are done and the max profit = 0.

```

**Constraints:**

	• `1 5`

	• `0 4`

---

-======================💡 Solution & Notes =====================-

INITIAL: 
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        if(len(prices) == 0):
            return 0
        left =1
        right = 1
        startPrice= prices[0]
        maxProfit = 0
        while right < len(prices):
            if startPrice > prices[right]:
                startPrice = prices[right]
                left = right
            maxProfit = max(prices[right] - startPrice, maxProfit)
            if(right + 1 > len(prices)):
                right = len(prices) -1
            else:
                right += 1
        return maxProfit
```
BETTER:
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        maxProfit = 0
        minValue = inf
        for price in prices:
            if price < minValue: 
                minValue = price
            elif((price - minValue) > maxProfit): maxProfit = price-minValue

            
        return maxProfit
```

# Approach
Explain your solution approach here...
just go through the array and track the minimum value and max profit and update
## Time Complexity
O(n)

## Space Complexity
O(1)

## Key Insights
- the difference in run time between the first one and second one, first one is sliding window and really slow
- Point 2
- Point 3

## Alternative Solutions
Discuss other approaches...
idk

---

## 🏷️ Tags
`Array` • `Dynamic Programming`

---

<div align="center">
  <sub>Generated with ❤️ by LeetCode Tracker</sub>
</div>