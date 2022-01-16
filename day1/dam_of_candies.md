---
title: "Two Pointer Technique"
description: "Dam of Candies"
categories:
  - Coding
  - Arrays
---

### Question

> Given an array of heights of books ,the task is to find out the area between two books that can hold the maximum candies without changing the original position of selected books. 

```
Input: N = 3, height[] = {1, 3, 4}
Output: 1
Explanation:
1. Area between book of height 1 and book of 
height 3 is 0 as there is no space between 
them.
2. Area between book of height 1 and book of 
height 4 is 1 by removing book of height 3.
3. Area between book of height 3 and book of 
height 4 is 0 as there is no space between them.
```

### Code [C++]

```C++

class Solution{
    
    public:
    int maxCandy(int height[], int n) 
    { 
        
        int area = 0;
        int i =0, j = n-1;
        while(i<j)
        {
            area = max(area , min(height[i], height[j]) * (j-i-1));
            if(height[i] > height[j]) j-=1;
            else i += 1;
        }
            
        
        return area;
    }   
};

```

> Time Complexity = O(N)

> Space Complexity = O(1)
