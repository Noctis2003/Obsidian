# Binary Tree Level Order Traversal

Solved 

Given a binary tree `root`, return the level order traversal of it as a nested list, where each sublist contains the values of nodes at a particular level in the tree, from left to right.

**Example 1:**

![](https://imagedelivery.net/CLfkmk9Wzy8_9HRyug4EVA/a4639809-0754-4eda-221f-a4cd58bd9c00/public)

```java
Input: root = [1,2,3,4,5,6,7]

Output: [[1],[2,3],[4,5,6,7]]
```

**Example 2:**

```java
Input: root = [1]

Output: [[1]]
```

**Example 3:**

```java
Input: root = []

Output: []
```

**Constraints:**

- `0 <= The number of nodes in the tree <= 1000`.
- `-1000 <= Node.val <= 1000`


```cpp
/**

 * Definition for a binary tree node.

 * struct TreeNode {

 *     int val;

 *     TreeNode *left;

 *     TreeNode *right;

 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}

 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}

 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}

 * };

 */

// how do you level order traversal a binary tree

// here it aws written to use a queue/

// but why a queue?

// let us first right the algorithm

// run rabbit run run rabbit run

class Solution {

public:

    vector<vector<int>> levelOrder(TreeNode* root) {

        vector<vector<int>>result;

         if(root==nullptr){

            return result;

        }

        queue<TreeNode *>q;

        q.push(root);

        while(!q.empty()){

           vector<int>level;

           int size=q.size();   // basically this loop is executed twice

                                // very ingenious algorithm

           for(int i=size;i>0;i--){

                TreeNode * front=q.front();

                q.pop();

                level.push_back(front->val);

                if(front->left){

                    q.push(front->left);

                }

                if(front->right){

                    q.push(front->right);

                }

                }

    result.push_back(level);

        }

        return result;

    }

};
```