[![](https://img.shields.io/github/stars/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby)
[![](https://img.shields.io/github/forks/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby/fork)

## 41\. First Missing Positive

Hard

Given an unsorted integer array `nums`, return the smallest missing positive integer.

You must implement an algorithm that runs in `O(n)` time and uses constant extra space.

**Example 1:**

**Input:** nums = [1,2,0]

**Output:** 3 

**Example 2:**

**Input:** nums = [3,4,-1,1]

**Output:** 2 

**Example 3:**

**Input:** nums = [7,8,9,11,12]

**Output:** 1 

**Constraints:**

*   <code>1 <= nums.length <= 5 * 10<sup>5</sup></code>
*   <code>-2<sup>31</sup> <= nums[i] <= 2<sup>31</sup> - 1</code>

## Solution

```php
<?php

namespace leetcode\g0001_0100\s0041_first_missing_positive;


class Solution {
    /**
     * @param Integer[] $nums
     * @return Integer
     */
    public function firstMissingPositive($nums) {
        $positiveNumbers = array_filter($nums, function ($num) {
            return $num > 0;
        });
        $positiveNumbers = array_flip($positiveNumbers);
        for ($i = 1; $i <= count($positiveNumbers) + 1; $i++) {
            if (isset($positiveNumbers[$i]) === false) {
                return $i;
            }
        }
    }
}
```