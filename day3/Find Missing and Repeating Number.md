---
title: "Find Repeating and Missing Number"
description: "Find Repeating and Missing Number"
categories:
  - Coding
  - Arrays
---

### Question

>Given an unsorted array Arr of size N of positive integers. One number 'A' from set {1, 2, …N} is missing and one number 'B' occurs twice in array. Find these two numbers.
```
Example 2:

Input:
N = 3
Arr[] = {1, 3, 3}
Output: 3 2
Explanation: Repeating number is 3 and 
smallest positive missing number is 2.

Your Task:
You don't need to read input or print anything. Your task is to complete the function findTwoElement() which takes the array of integers arr and n as parameters and returns an array of integers of size 2 denoting the answer ( The first index contains B and second index contains A.)
```

### Code [C++]

```C++


// { Driver Code Starts
#include <bits/stdc++.h>

using namespace std;

 // } Driver Code Ends
class Solution{
public:
    int arr2[2];
    int *findTwoElement(int *arr, int n) {
    
        int hsh[n+1];
        
        for(int i = 0 ; i<=n ; i++)
        {
            hsh[i] = 0;
        }
        
        for(int i = 0; i<n; i++)
        {
            hsh[arr[i]]++;
        }
        
        for(int i = 0 ; i<= n; i++)
        {
            if(hsh[i] == 2) arr2[0] = i;
            if(hsh[i] == 0) arr2[1] = i;
        }
        
        return arr2;
    }
};



// { Driver Code Starts.

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        int a[n];
        for (int i = 0; i < n; i++) {
            cin >> a[i];
        }
        Solution ob;
        auto ans = ob.findTwoElement(a, n);
        cout << ans[0] << " " << ans[1] << "\n";
    }
    return 0;
}  // } Driver Code Ends


```

> Time Complexity = O(N)

> Space Complexity = O(1)

```
Constraints:
1 ≤ N ≤ 105
1 ≤ Arr[i] ≤ N
```

