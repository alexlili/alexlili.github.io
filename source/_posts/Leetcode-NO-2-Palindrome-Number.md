---
title: Leetcode NO.2 Palindrome Number
---
## Description

Givren an integer x , return true if x is a palindrome, and false otherwise.

Example 1:

```javascript
Input: x=121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

Example 2:

```javascript
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

Example 3:

```javascript
Inout: x = 10
Output: false
Explanationg: Reads 01 from right to left. Therefore it is not a palindrome.
```

## Soulution

###### Solution 1:

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
  const y = x.toString().split('').reverse().join('');
  if(x==Number(y)) return true
  return false
};
```

###### Explanation:

The javascript method of array-reverse is used in this solution. And you need to change the data format from number to string first. Then split it into an array. But it has a risk about integer overflow when the x is reversed.

###### Solution 2:

```javascript
/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
  if(x<0||x%10==0&&x!=0) return false
  let revertNumber = 0
  while(x<revertNumber){
    revertNumber = x*10+x%10
    x = x/10
  }
  return x===revertNumber||x===revertNumber/10
};
```

###### Explanation:

This solution avoid the risk of integer overflow. The key is to find the revertNumber using a loop. If x is an odd number and x is equal to revertNumber/10(cause revertNumber has the middle number, so we must remove the middle number) after the while-loop , the function returns true. If x is an even number , we just judge whether x is equal to revertNumber after the while-loop.
