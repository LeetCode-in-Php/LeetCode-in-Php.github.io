[![](https://img.shields.io/github/stars/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby)
[![](https://img.shields.io/github/forks/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby/fork)

## 6\. Zigzag Conversion

Medium

The string `"PAYPALISHIRING"` is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P A H N A P L S I I G Y I R 

And then read line by line: `"PAHNAPLSIIGYIR"`

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows); 

**Example 1:**

**Input:** s = "PAYPALISHIRING", numRows = 3

**Output:** "PAHNAPLSIIGYIR" 

**Example 2:**

**Input:** s = "PAYPALISHIRING", numRows = 4

**Output:** "PINALSIGYAHRPI"

**Explanation:** P I N A L S I G Y A H R P I 

**Example 3:**

**Input:** s = "A", numRows = 1

**Output:** "A" 

**Constraints:**

*   `1 <= s.length <= 1000`
*   `s` consists of English letters (lower-case and upper-case), `','` and `'.'`.
*   `1 <= numRows <= 1000`

## Solution

```php
<?php

namespace leetcode\g0001_0100\s0006_zigzag_conversion;


class Solution {
    /**
     * @param String $s
     * @param Integer $numRows
     * @return String
     */
    public function convert($s, $numRows) {
        if ($numRows == 1) {
            return $s;
        }
        $row = 0;
        $col = 0;
        $dir = 'down';
        for ($i = 0; $i < strlen($s); $i++) {
            $string[$row][] = $s[$i];
            if ($row < $numRows - 1 && $dir == 'down') {
                $row++;
            } elseif ($row == $numRows - 1 && $dir == 'down') {
                $row--;
                $dir = 'up';
                $col++;
            } elseif ($row > 0) {
                $row--;
                $col++;
            } else {
                $dir = 'down';
                $row++;
            }
        }
        return implode(array_merge(...$string));
    }
}
```