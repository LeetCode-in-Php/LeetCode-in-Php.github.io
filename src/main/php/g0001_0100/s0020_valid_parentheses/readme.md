[![](https://img.shields.io/github/stars/LeetCode-in-Php/LeetCode-in-Php?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php)
[![](https://img.shields.io/github/forks/LeetCode-in-Php/LeetCode-in-Php?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php/fork)

## 20\. Valid Parentheses

Easy

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1.  Open brackets must be closed by the same type of brackets.
2.  Open brackets must be closed in the correct order.

**Example 1:**

**Input:** s = "()"

**Output:** true 

**Example 2:**

**Input:** s = "()[]{}"

**Output:** true 

**Example 3:**

**Input:** s = "(]"

**Output:** false 

**Example 4:**

**Input:** s = "([)]"

**Output:** false 

**Example 5:**

**Input:** s = "{[]}"

**Output:** true 

**Constraints:**

*   <code>1 <= s.length <= 10<sup>4</sup></code>
*   `s` consists of parentheses only `'()[]{}'`.

## Solution

```php
class Solution {
    /**
     * @param String $s
     * @return Boolean
     */
    public function isValid($s) {
        $stack = [];
        $length = strlen($s);
        for ($i = 0; $i < $length; $i++) {
            $c = $s[$i];
            if ($c == '(' || $c == '[' || $c == '{') {
                array_push($stack, $c);
            } elseif (($c == ')' && !empty($stack) && end($stack) == '(')
                || ($c == '}' && !empty($stack) && end($stack) == '{')
                || ($c == ']' && !empty($stack) && end($stack) == '[')
            ) {
                array_pop($stack);
            } else {
                return false;
            }
        }
        return empty($stack);
    }
}
```