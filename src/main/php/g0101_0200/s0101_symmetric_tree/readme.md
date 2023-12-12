[![](https://img.shields.io/github/stars/LeetCode-in-Php/LeetCode-in-Php?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php)
[![](https://img.shields.io/github/forks/LeetCode-in-Php/LeetCode-in-Php?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Php/LeetCode-in-Php/fork)

## 101\. Symmetric Tree

Easy

Given the `root` of a binary tree, _check whether it is a mirror of itself_ (i.e., symmetric around its center).

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/02/19/symtree1.jpg)

**Input:** root = [1,2,2,3,4,4,3]

**Output:** true 

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/02/19/symtree2.jpg)

**Input:** root = [1,2,2,null,3,null,3]

**Output:** false 

**Constraints:**

*   The number of nodes in the tree is in the range `[1, 1000]`.
*   `-100 <= Node.val <= 100`

**Follow up:** Could you solve it both recursively and iteratively?

## Solution

```php
/**
 * Definition for a binary tree node.
 * class TreeNode {
 *     public $val = null;
 *     public $left = null;
 *     public $right = null;
 *     function __construct($val = 0, $left = null, $right = null) {
 *         $this->val = $val;
 *         $this->left = $left;
 *         $this->right = $right;
 *     }
 * }
 */
class Solution {
    /**
     * @param TreeNode $root
     * @return Boolean
     */
    function isSymmetric($root) {
        if ($root == null) {
            return true;
        }
        return $this->helper($root->left, $root->right);
    }

    private function helper($leftNode, $rightNode) {
        if ($leftNode == null || $rightNode == null) {
            return $leftNode == null && $rightNode == null;
        }
        if ($leftNode->val != $rightNode->val) {
            return false;
        }
        return $this->helper($leftNode->left, $rightNode->right) && $this->helper($leftNode->right, $rightNode->left);
    }
}
```