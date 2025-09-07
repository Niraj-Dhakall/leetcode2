# 📝 Climbing Stairs

<div align="center">

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Date](https://img.shields.io/badge/Date-9--6--2025-blue)
![Math](https://img.shields.io/badge/Math-lightgrey)
![Dynamic Programming](https://img.shields.io/badge/Dynamic%20Programming-lightgrey)
![Memoization](https://img.shields.io/badge/Memoization-lightgrey)

</div>

---

## 🔗 Problem Link
**[Climbing Stairs on LeetCode](https://leetcode.com/problems/climbing-stairs)**

---

## 📋 Problem Statement

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

**Example 1:**

**Input:** n = 2
**Output:** 2
**Explanation:** There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

```

**Example 2:**

**Input:** n = 3
**Output:** 3
**Explanation:** There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

```

**Constraints:**

	• `1 <= n <= 45`

---

-======================💡 Solution & Notes =====================-


```python
class Solution:
    def climbStairs(self, n: int) -> int:
        if n == 1: // if there is one step, then there is only one way
            return 1
        first,second = 1, 2 

        for _ in range(3, n+1): // it is just like a fibonacci
            first,second = second, first+ second 
                            // starting at the 3rd step, there is 3 ways of getting there
                            // take 1 step, then a 2nd
                            // take two steps then one
                            // take 3 1 steps
                            //for a total of 3 ways

                            // Then moving to the 4th step, 
                            // you can take 4 1 steps : 1 way
                            // go: 1 -> 3 -> 4 for a second way
                            // go 2 -> 4 for a third way
                            // go 2 -> 3 -> 4 for a fourth way
                            // go 1 -> 2 -> 4 for a 5th way

        return second // second keeps track of both the ONE steps and the TWO steps
```
# Approach
Explain your solution approach here...

Essentially, we know that for step 1, there is one way, and for step 2 there are two ways.
So we set first = 1 (ways to climb 1 step) and second = 2 (ways to climb 2 steps).

Each time we move up a step, we update these two values.

Before each move:

**first** holds the number of ways to reach the step **two** below (i-2)

**second** holds the number of ways to reach the **previous** step (i-1)

When we climb to the next step (i):

We shift forward: first takes on the old second (it now represents i-1)

We recalculate second as the sum of the old first and old second, because:

ways(i) = ways(i-1) + ways(i-2)

==============================================================



There is 1 way to get to the first step.
There are 2 ways to get to the second step.

Starting at the third step:

first holds the number of ways to get to step 2 (the step two below the current one).

We then compute the new number of ways (second) as the sum of the ways to the two previous steps — because any path to the current step must come from either one step down or two steps down.

## Time Complexity
O(n)

## Space Complexity
O(1)

## Key Insights
- fibonacci but a little tweaked
- dynamic programming, storing the data from previous
- this one was really fun to learn

## Alternative Solutions
idk


---

## 🏷️ Tags
`Math` • `Dynamic Programming` • `Memoization`

---

<div align="center">
  <sub>Generated with ❤️ by LeetCode Tracker</sub>
</div>
