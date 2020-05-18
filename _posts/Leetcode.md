---
layout:     post
title:      This is the Leetcode record
date:       2020-05-14
author:     Zichao
header-img: img/ghostdoll.jpeg
catalog: true
tags:
    - leetcode
    - paper
---

# Leetcode

## 2020-05-02

### 26. Remove Duplicates from Sorted Array

Use two pointers. One fast pointer and one slow pointer. The array is sorted so that we only need to check the consistency in this array. When there are differeces occuring, we need to put that 
difference number in the correct place. We use the slow pointer to identify the correct place and use the fast pointer to go through this whole array. The time complexity is O(n) and space 
complexity is O(1).

```
    class Solution {
    public int removeDuplicates(int[] nums) {
        
        if(nums == null || nums.length == 0) {
            return 0;
        }
        
        int fast = 1;
        
        int slow = 0;
        
        while(fast<nums.length) {
            
            if(nums[slow]!=nums[fast]) {
                slow++;
                
                nums[slow] = nums[fast];
            }
            
            fast++;
            
            
        }
        
        return slow+1;
        
    }
}
```

## 2020-05-14

### 162. Find Peak Element
利用二分法，只要是Peak的点必定会比其两边的点大，先判断mid左边的点是否比mid大，如果大就向左移动，再判断mid右边的点是否比mid大，如果大就向右移动，如果都不是的话那么这个mid就是要找的点，end=mid继续循环，最后把剩下的两个点进行一下比较即可，要注意越界问题
```
    class Solution {
    public int findPeakElement(int[] nums) {
        
        if(nums == null || nums.length == 0) {
            return 0;
        }
        
        int start = 0;
        
        int end = nums.length-1;
        
        while(start + 1 < end) {
            int mid = start + (end - start)/2;
            int temp1 = 0;
            if(mid - 1<0) {
                temp1 = Integer.MIN_VALUE;
            } else {
                temp1 = nums[mid - 1];
            }
            int temp2 = 0;
            if(mid + 1>nums.length-1) {
                temp2 = Integer.MIN_VALUE;
            } else {
                temp2 = nums[mid+1];
            }
            if(nums[mid]<temp1) {
                end = mid;
            } else if(nums[mid]<temp2) {
                start = mid;
            } else {
                end = mid;
            }
            
        }
        
        if(nums[start]>nums[end]) {
            return start;
        } else 
            return end;
        
        }
    }
```

## 2020-05-18

### 63.Unique Paths II
动态规划，确定最后一步得状态，最后一步的子问题，列出转移方程，注意处理图中特殊的点，比如有障碍或者在边上
```
    class Solution {
    public int uniquePathsWithObstacles(int[][] obstacleGrid) {
        
        int m = obstacleGrid.length;
        
        if(m == 0) {
            return 0;
        }
        
        int n = obstacleGrid[0].length;
        
        if(n == 0) {
            return 0;
        }
        
        int[][] dp = new int[m][n];
        
        for(int i = 0; i<m; i++) {
            for(int j = 0; j < n; j++) {
                
                if(obstacleGrid[i][j] == 1) {
                    dp[i][j] = 0;
                    continue;
                        
                }
                
                if(i == 0 && j == 0) {
                    dp[i][j] = 1;
                    continue;
                }
                
                if(i > 0) {
                    dp[i][j] += dp[i-1][j];
                }
                
                if(j > 0) {
                    dp[i][j] += dp[i][j-1];
                }
                
            }
        }
        
        return dp[m-1][n-1];
        
        }
    }
```