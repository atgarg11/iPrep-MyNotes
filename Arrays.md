# Subarray sum problems:
    Multiple Flavors of these problems and some standard techniques
### Techniques
* Sliding Window
** This technique is useful if there are no negative numbers in the array
* Prefix Sum
** Use this if there are negative numbers present
* Two Pointer
#### Examples
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
