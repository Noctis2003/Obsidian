```cpp
class Solution {

public:

//  HCF of 4 and 6 is equal to 2  

// what does GCD of str1 and str 2

int gcd(int n_1, int n_2) {

    while (n_1 != 0 && n_2 != 0) {

        int x = n_1 % n_2;

        n_1 = n_2;

        n_2 = x;

    }

    return (n_1 == 0) ? n_2 : n_1;

}

  

    string gcdOfStrings(string str1, string str2) {

          if(str1+str2!=str2+str1){

            return "";

          }

          return str1.substr(0,gcd(str1.size(),str2.size()));

    }

};
```

# Greatest Common Divisor of Strings

Solved 

For two strings `s` and `t`, we say "`t` divides `s`" if and only if `s = t + t + t + ... + t + t` (i.e., `t` is concatenated with itself one or more times).

You are given two strings `str1` and `str2`, return the largest string `x` such that `x` divides both `str1` and `str2`. If there is no such string, return `""`.

**Example 1:**

```java
Input: str1 = "ABAB", str2 = "AB"

Output: "AB"
```

**Example 2:**

```java
Input: str1 = "NANANA", str2 = "NANA"

Output: "NA"
```

**Constraints:**

- `1 <= str1.length, str2.length <= 1000`
- `str1` and `str2` consist of English uppercase letters.