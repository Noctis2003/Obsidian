# Asteroid Collision

Solved 

You are given an array `asteroids` of integers representing asteroids in a row. The indices of the asteriod in the array represent their relative position in space.

For each asteroid, the absolute value represents its size, and the sign represents its direction (positive meaning right, negative meaning left). Each asteroid moves at the same speed.

Find out the state of the asteroids after all collisions. If two asteroids meet, the smaller one will explode. If both are the same size, both will explode. Two asteroids moving in the same direction will never meet.

**Example 1:**

```java
Input: asteroids = [2,4,-4,-1]

Output: [2]
```

**Example 2:**

```java
Input: asteroids = [5,5]

Output: [5,5]
```

**Example 3:**

```java
Input: asteroids = [7,-3,9]

Output: [7,9]
```




```cpp
class Solution {

public:

    vector<int> asteroidCollision(vector<int>& asteroids) {

     // let us do this question the proper way

     // this is a question of stack

     // how shall i do it?

     // this is a question of stack of an asteroid collision

     // fuck u suc my dic

     vector<int>s;

    // if the top of the stack is negative and the number added is also

    // negative what i want you to do is push the neg number

    // if top is positive and number is negative we will destory something

    // but what shall we destroy?

    for(int i=0;i<asteroids.size();i++){
        if(s.empty()){
            s.push_back(asteroids[i]);
            continue;
        }

        // another thing that we can do--

        if(s.back()<0 && asteroids[i]<0){
            s.push_back(asteroids[i]);
        }
        else if(s.back()>0 && asteroids[i]>0){
            s.push_back(asteroids[i]);
        }
        else if(s.back()>0 && asteroids[i]<0){
            bool isDestroyed=false;
            while(!s.empty() && !isDestroyed && s.back()>0){
                if(s.back()<abs(asteroids[i])){
                    s.pop_back();
                }
                else if(s.back()==abs(asteroids[i])){
                    s.pop_back();
                    isDestroyed=true;
                    break;
                }
                else if(s.back()>abs(asteroids[i])){
                    isDestroyed=true;
                    break;
                }
            }
            if(!isDestroyed){
                s.push_back(asteroids[i]);
            }
        }
        else if(s.back()<0 && asteroids[i]>0){
            s.push_back(asteroids[i]);
        }
    }
    return s;    
    }
};
```