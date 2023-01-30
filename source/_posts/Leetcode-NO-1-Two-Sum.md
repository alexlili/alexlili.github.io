---
title: Leetcode NO.1 Two Sum
---
## Description

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly on solution ,and you may not use the same element twice.

You can return the answer in any order.

Example :

```javascript
Input :nums = [2,7,11,15],target = 9
Output: [0,1]
Explanation : Because nums[0] + nums[1] == 9 , we return [0,1].
```

## Solution

###### Solution 1:

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  for (let i=0;i<nums.length;i++){
    if(nums.indexOf(target-nums[i])!=-1&&i!=nums.indexOf(target-nums[i])){
      return [i,nums.indexOf(target-nums[i])]
    }
  }
};
```

###### Explanation:

This solution use the method, indexOf, to find the indice of the target.

###### Solution 2:

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  let diff = new Map()
  for(let i=0;i<nums.length;i++){
    if(diff.has(target-nums[i])){
      return [i,diff.get(target-nums[i])]
    }
    diff.set(nums[i],i)
  }
};
```

###### Explanation:

This solution use a data structure-map.It looks like the Object (key-value) in javascript. This solution is the best currently.
