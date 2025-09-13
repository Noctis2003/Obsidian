# Insert into a Binary Search Tree

Solved 

You are given the `root` node of a binary search tree (BST) and a value `val` to insert into the tree. Return the root node of the BST after the insertion. It is **guaranteed** that the new value does not exist in the original BST.

Note: There may exist multiple valid ways for the insertion, as long as the tree remains a BST after insertion. You can return any of them.

**Example 1:**

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/d440bea8-83c9-418e-edb3-7afb573eba00/public)

```java
Input: root = [5,3,9,1,4], val = 6

Output: [5,3,9,1,4,6]
```

**Example 2:**

```java
Input: root = [5,3,6,null,4,null,10,null,null,7], val = 9

Output: [5,3,6,null,4,null,10,null,null,7,null,null,9]
```

**Constraints:**

- `0 <= The number of nodes in the tree <= 10,000`.
- `-100,000,000 <= val, Node.val <= 100,000,000`
- All the values `Node.val` are unique.
- It's **guaranteed** that `val` does not exist in the original BST.




```cpp
class Solution {

public:

    TreeNode* insertIntoBST(TreeNode* root, int val) {

        if (!root) return new TreeNode(val); // empty tree case

  

        TreeNode* holder = root;

  

        while (true) {

            if (val > holder->val) {

                if (!holder->right) {

                    holder->right = new TreeNode(val);

                    break;

                }

                holder = holder->right;

            } else { // val < holder->val

                if (!holder->left) {

                    holder->left = new TreeNode(val);

                    break;

                }

                holder = holder->left;

            }

        }

  

        return root;

    }

};
```