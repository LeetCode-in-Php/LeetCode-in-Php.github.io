[![](https://img.shields.io/github/stars/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby)
[![](https://img.shields.io/github/forks/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby/fork)

## 78\. Subsets

Medium

Given an integer array `nums` of **unique** elements, return _all possible subsets (the power set)_.

The solution set **must not** contain duplicate subsets. Return the solution in **any order**.

**Example 1:**

**Input:** nums = [1,2,3]

**Output:** [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]] 

**Example 2:**

**Input:** nums = [0]

**Output:** [[],[0]] 

**Constraints:**

*   `1 <= nums.length <= 10`
*   `-10 <= nums[i] <= 10`
*   All the numbers of `nums` are **unique**.

## Solution

```php
<?php

namespace leetcode\g0001_0100\s0078_subsets;


class Solution {
    /**
     * @param Integer[] $nums
     * @return Integer[][]
     */
    public function subsets($nums) {
        $res = array();
        $this->solve($nums, array(), $res, 0);
        return $res;
    }

    private function solve($nums, $temp, &$res, $start) {
        array_push($res, $temp);
        for ($i = $start; $i < count($nums); $i++) {
            array_push($temp, $nums[$i]);
            $this->solve($nums, $temp, $res, $i + 1);
            array_pop($temp);
        }
    }
}
```