# Koko Eating Bananas

Solved 

You are given an integer array `piles` where `piles[i]` is the number of bananas in the `ith` pile. You are also given an integer `h`, which represents the number of hours you have to eat all the bananas.

You may decide your bananas-per-hour eating rate of `k`. Each hour, you may choose a pile of bananas and eats `k` bananas from that pile. If the pile has less than `k` bananas, you may finish eating the pile but you can not eat from another pile in the same hour.

Return the minimum integer `k` such that you can eat all the bananas within `h` hours.

**Example 1:**

```java
Input: piles = [1,4,3,2], h = 9

Output: 2
```

Explanation: With an eating rate of 2, you can eat the bananas in 6 hours. With an eating rate of 1, you would need 10 hours to eat all the bananas (which exceeds h=9), thus the minimum eating rate is 2.

**Example 2:**

```java
Input: piles = [25,10,23,4], h = 4

Output: 25
```



```cpp
class Solution {

public:

    int calculate(vector<int>piles,int val){

        int sum=0;

        // being a skiled developer

        // you must appreciate the beauty of this question deeply

        // you are using

        for(int i=0;i<piles.size();i++){

            sum=sum+ceil(double(piles[i])/val);

        }

        return sum;

    }

    int minEatingSpeed(vector<int>& piles, int h) {

     // pretty good

     // pretty neat n clean  

        // first we shall sort i

        int ans=0;

        int n=piles.size()-1;

        int high = *max_element(piles.begin(), piles.end());

        int low=1;

        while(low<=high){

            int mid=high-(high-low)/2;

            int val=calculate(piles,mid);

            if(val<=h){

                ans=mid;

                high=mid-1;

            }

            else if(val>h){ // increase your eating rate

                low=mid+1;

            }

        }

        return ans;

  

    }

};
```