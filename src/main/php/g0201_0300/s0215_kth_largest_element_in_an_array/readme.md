[![](https://img.shields.io/github/stars/LeetCode-in-Php/LeetCode-in-Php?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php)
[![](https://img.shields.io/github/forks/LeetCode-in-Php/LeetCode-in-Php?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php/fork)

## 215\. Kth Largest Element in an Array

Medium

Given an integer array `nums` and an integer `k`, return _the_ <code>k<sup>th</sup></code> _largest element in the array_.

Note that it is the <code>k<sup>th</sup></code> largest element in the sorted order, not the <code>k<sup>th</sup></code> distinct element.

**Example 1:**

**Input:** nums = [3,2,1,5,6,4], k = 2

**Output:** 5 

**Example 2:**

**Input:** nums = [3,2,3,1,2,4,5,5,6], k = 4

**Output:** 4 

**Constraints:**

*   <code>1 <= k <= nums.length <= 10<sup>4</sup></code>
*   <code>-10<sup>4</sup> <= nums[i] <= 10<sup>4</sup></code>

## Solution

```php
class Solution {
    /**
     * @param Integer[] $nums
     * @param Integer $k
     * @return Integer
     */
    function findKthLargest($nums, $k) {
        $n = count($nums);
        sort($nums);
        return $nums[$n - $k];
    }
}
```