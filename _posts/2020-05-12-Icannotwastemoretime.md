---
layout:     post
title:      Nobody can judge me
subtitle:   No time to waste
date:       2020-05-12
author:     Zichao
header-img: img/ghostdoll.jpeg
catalog: true
tags:
    - leetcode
    - paper
---

# 5/12/2020

- [ ]  BFS练习

- [ ]  背诵leetcode 5 道题

- [ ]  EVA

- [ ]  JavaScript restart

- [ ]  Spring

- [ ]  C++ start

每天过的都好没有意思，刷题还是进行的很艰难，科研也不会做

## LeetCode

二分法模板，注意循环退出条件是start + 1 < end
二分法：
```
    class Solution {
        public int binarySearch(int[] nums, int target) {

            if(nums == null || nums.length == 0) {
                return -1;
            }

            int start = 0;

            int end = nums.length - 1;

            while (start + 1 < end) {
                int mid = start + (end - start)/2;
                if(nums[mid] == target) {
                    end = mid;
                }
                else if(nums[mid] < target ) {
                    start = mid;
                }
                else {
                    end = mid;
                }
            }

            if(nums[start] == target) {
                return start;
            }
            if(nums[end] == target) {
                return end;
            }

            return -1;




        }
    }
```

### Lintcode 447 Search in a big Sorted Array
先使用倍增法从开头的1找到其应该截止的位置，再从0和该位置进行二分查找
```
    public class Solution {
    /**
     * @param reader: An instance of ArrayReader.
     * @param target: An integer
     * @return: An integer which is the first index of target.
     */
    public int searchBigSortedArray(ArrayReader reader, int target) {
        // write your code here
        int start = 0; 
        int end = 1;
        while(reader.get(end) < target) {
            end = end *2;
        }
        
        while(start + 1< end) {
            int mid = start + (end - start)/2;
            if(reader.get(mid) == target) {
                end = mid;
            }
            else if(reader.get(mid) < target) {
                start = mid;
            }
            else {
                end = mid;
            }
        }
        
        if(reader.get(start) == target) {
            return start;
        }
        if(reader.get(end) == target) {
            return end;
        }
        
        return -1;
        
        
        }
    }
```

### Leetcode 658 Find K closest Elements
首先找出来目标在哪里，借助二分法找出来，再从目标向两边寻找找到最接近的
```
    import java.util.*; 
class Solution {
    public List<Integer> findClosestElements(int[] arr, int k, int x) {
        
        int[] res = new int[k];
        
        if(arr == null || arr.length == 0) {
            List<Integer> ans =  new ArrayList<>();
            
            for(int ch:res) {
                ans.add(ch);
            }
            return ans;
        }
        
        if(arr.length < k) {
            List<Integer> ans =  new ArrayList<>();
            
            for(int ch:res) {
                ans.add(ch);
            }
            return ans;
        }
        
        int index = helper(arr, x);
        
        int start = index - 1;
        
        int end = index;
        
        for(int i = 0; i<k; i++) {
            if(start < 0) {
                res[i] = arr[end++];
            }
            else if(end >= arr.length) {
                res[i]  = arr[start--];
            }
                else {
                    if(x - arr[start] <= arr[end] - x) {
                        res[i] = arr[start --];
                    }
                    else {
                        res[i] = arr[end++];
                    }
                }
            }
        
       List<Integer> ans =  new ArrayList<>();
        
        
            
            for(int ch:res) {
                ans.add(ch);
            }
        
        Collections.sort(ans);
    
       return ans;
        
    }
    
    private int helper(int[] arr, int x) {
        int start = 0;
        
        int end = arr.length-1;
        
        while(start + 1< end) {
            int mid = start + (end - start)/2;
            
            if(arr[mid] == x) {
                end = mid;
            }
            else if(arr[mid] < x) {
                start = mid;
            }
            else {
                end = mid;
            }
        }
        
        if(arr[start] >= x) {
            return start;
        }
        if(arr[end] >= x) {
            return end;
        }
        
        return arr.length;
        }
    }
```