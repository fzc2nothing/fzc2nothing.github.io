---
layout:     post
title:      不给自己留遗憾
subtitle:   第二天
date:       2020-05-03
author:     Zichao
header-img: img/ghostdoll.jpeg
catalog: true
tags:
    - iOS
    - 轮子
---


>**Summer Schedule** 以每一周为分割

# 5/3/2020

完成CS 61B第一次作业，看完第二个视频

刷完ladder1题目

看完JS一节

看完bootcamp一节

完成简历修改



## Web develop

bootstrap

Jumbotron

container

Nav Bars

## LeetCode

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

## BloodBorne:
    发现代言人阿梅利亚



