# Daily Temperatures

You are given an array of integers `temperatures` where `temperatures[i]` represents the daily temperatures on the `ith` day.

Return an array `result` where `result[i]` is the number of days after the `ith` day before a warmer temperature appears on a future day. If there is no day in the future where a warmer temperature will appear for the `ith` day, set `result[i]` to `0` instead.

**Example 1:**

```java
Input: temperatures = [30,38,30,36,35,40,28]

Output: [1,4,1,2,1,0,0]
```

**Example 2:**

```java
Input: temperatures = [22,21,20]

Output: [0,0,0]
```

**Constraints:**

- `1 <= temperatures.length <= 1000`.
- `1 <= temperatures[i] <= 100`


```cpp
class Solution {

public:

    vector<int> dailyTemperatures(vector<int>& temperatures) {

       // we have to return an array that shall give us the

       // no of days till we see a recorded higher temperature

       // but what after that?

       // what can we do after that

        // how do we solve this problem

  

        stack<int>s;

        int n=temperatures.size()-1;

         vector<int>ans(n,0);

         for(int i=0;i<temperatures.size();i++){

            while(!s.empty() && temperatures[i]>temperatures[s.top()]){

                int prev=s.top();

                s.pop();

                ans[prev]=i-prev;

            }

            s.push(i);

         }

         return ans;

  

    }

};
```