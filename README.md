# LeetCode 101 — Symmetric Tree

## Problem
Given the `root` of a binary tree, check whether it is a mirror of itself (symmetric around its center).

---

## Example

Input:
```text
root = [1,2,2,3,4,4,3]
```

Output:
```text
true
```

---

## Approach
Use DFS recursion:

- Compare left subtree with right subtree
- Two trees are symmetric if:
  - Their values are equal
  - Left child of first tree matches right child of second tree
  - Right child of first tree matches left child of second tree

---

## Java Solution

```java
class Solution {

    public boolean isSymmetric(TreeNode root) 
    {
        if(root == null)
        {
            return true;
        }

        return check(root.left, root.right);
    }

    public boolean check(TreeNode left, TreeNode right)
    {
        if(left == null && right == null)
        {
            return true;
        }

        if(left == null || right == null)
        {
            return false;
        }

        if(left.val != right.val)
        {
            return false;
        }

        return check(left.left, right.right) &&
               check(left.right, right.left);
    }
}
```

---

## Time Complexity
```text
O(n)
```

Each node is visited once.

---

## Space Complexity
```text
O(h)
```

- `h` = height of tree
- Recursive stack space

---

## Key Concepts
- Binary Tree
- DFS
- Recursion
- Mirror Tree
- Tree Traversal
