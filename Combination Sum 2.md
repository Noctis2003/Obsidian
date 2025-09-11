```cpp
class Solution {
public:
    void dfs(int i, int target, vector<int>& candidates, 
             vector<int>& subset, vector<vector<int>>& result) {
        if (target == 0) {
            result.push_back(subset);
            return;
        }
        if (i >= candidates.size() || target < 0) return;

        // PICK: include current element
        subset.push_back(candidates[i]);
        dfs(i + 1, target - candidates[i], candidates, subset, result);
        subset.pop_back();

        // DON'T PICK: skip current element
        // BUT skip all duplicates of candidates[i]
        int j = i + 1;
        while (j < candidates.size() && candidates[j] == candidates[i]) j++;
        dfs(j, target, candidates, subset, result);
    }

    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        sort(candidates.begin(), candidates.end()); // important for duplicates
        vector<vector<int>> result;
        vector<int> subset;
        dfs(0, target, candidates, subset, result);
        return result;
    }
};

```

# Combination Sum II

You are given an array of integers `candidates`, which may contain duplicates, and a target integer `target`. Your task is to return a list of all **unique combinations** of `candidates` where the chosen numbers sum to `target`.

Each element from `candidates` may be chosen **at most once** within a combination. The solution set must not contain duplicate combinations.

You may return the combinations in **any order** and the order of the numbers in each combination can be in **any order**.

**Example 1:**

```java
Input: candidates = [9,2,2,4,6,1,5], target = 8

Output: [
  [1,2,5],
  [2,2,4],
  [2,6]
]
```

**Example 2:**

```java
Input: candidates = [1,2,3,4,5], target = 7

Output: [
  [1,2,4],
  [2,5],
  [3,4]
]
```