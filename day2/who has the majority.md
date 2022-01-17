---
title: "Who has the majority"
description: "Who has the majority"
categories:
  - Coding
  - Arrays
---

### Question

> Given an array arr[] of size N and two elements x and y, use counter variables to find which element appears most in the array, x or y. If both elements have the same frequency, then return the smaller element.
Note:  We need to return the element, not its count.
```
Input:
N = 8
arr[] = {1,2,3,4,5,6,7,8}
x = 1, y = 7
Output: 1
Explanation: 
frequency of 1 is 1.
frequency of 7 is 1.
Since 1 < 7, return 1.
```

### Code [C++]

```C++


class Solution{
  public:
    // Function to find element with more appearances between two elements in an
    // array.
    int majorityWins(int arr[], int n, int x, int y) {
        // code here
        int min = ((x<y) ? x : y);
        int xcounter = 0, ycounter = 0;
        for(int i = 0; i<n; i++)
        {
            if(arr[i] == x) xcounter++;
            else if(arr[i] == y) ycounter++;
        }
        if(xcounter == ycounter) return min;
        else return ((xcounter>ycounter)? x : y);
    }
};


```

> Time Complexity = O(N)

> Space Complexity = O(1)

