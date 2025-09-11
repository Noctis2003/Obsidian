# Permutations

Solved 

Given an array `nums` of **unique** integers, return all the possible permutations. You may return the answer in **any order**.

**Example 1:**

```java
Input: nums = [1,2,3]

Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
```

**Example 2:**

```java
Input: nums = [7]

Output: [[7]]
```

```cpp
class Solution {

public:

// we can return the answer in any order

// i wonder how to do this

// i guess that is how you do it

// i still do not get this question

  

    void solve(vector<vector<int>>&result,vector<int>&perm,vector<bool>&used,vector<int>nums){

        if(perm.size()==nums.size()){

            result.push_back(perm);

            return;

                }

        for(int i=0;i<nums.size();i++){

            if(used[i]){

                continue;

            }  

            used[i]=true;

            perm.push_back(nums[i]);

            solve(result,perm,used,nums);

            perm.pop_back();

            used[i]=false;

        }

    }

    vector<vector<int>> permute(vector<int>& nums) {

        vector<bool>used(nums.size(),false);

        vector<int>perm;

        vector<vector<int>>result;

        solve(result,perm,used,nums);

        return result;

    }

};
```