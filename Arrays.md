# Subarray sum problems:
    Multiple Flavors of these problems and some standard techniques
## Techniques
* Sliding Window
** This technique is useful if there are no negative numbers in the array
* Prefix Sum
** Use this if there are negative numbers present
* Two Pointer
### Examples
[325. Maximum Size Subarray Sum Equals k](https://leetcode.com/problems/maximum-size-subarray-sum-equals-k/)

__Squares of Sorted Array__:
* Think of it as merge Sort of two sorted arrays. Pick the bigger element from each array.
```
vector<int> sortedSquares(vector<int>& nums) {
        int i = 0, j = nums.size()-1;
        int k=j;
        vector<int> res(j+1);
        while ( i <= j) {
            if ( abs(nums[i]) > abs(nums[j])) {
                res[k--] = nums[i]*nums[i];
                i++;
            } else {
                res[k--] = nums[j]*nums[j];
                j--;
            }
        }
        return res;
    }
```
## 2Sum / 3Sum problems
* hash solution
* two pointer with sorting [ Best approach  ]
* 
```
sort(nums.begin(), nums.end());
        for ( i = 0; i < len-2; i++) {
            if ( prev == nums[i]) continue; //Important to skip duplicates
            prev = nums[i];
            tmpSum = -nums[i];
            // find 2 sum for k
            for ( j = i+1, k = len-1; j < k; ) {
                if ( prevj == nums[j] && prevk == nums[k]) { 
                    j++; k--; // IMportant to skip duplicates
                }
                else if ( nums[j]+nums[k] == tmpSum) {
                    tmp[0] = nums[i];
                    tmp[1] = nums[j];
                    tmp[2] = nums[k];
                    res.push_back(tmp);
                    prevj = nums[j];
                    prevk = nums[k];
                    j++; k--;  
                } else if ( nums[j]+nums[k] < tmpSum) {
                    prevj = nums[j];
                    j++;
                } else {
                    prevk = nums[k];
                    k--;            
                }
            }
        }
```
