---
title: 'leetcode day1:Reverse Integer（easy）'
tags: []
originContent: ''
categories: []
toc: false
date: 2020-01-01 19:52:27
desleetocde第一天。
---

leetocde第一天。
> 原题链接：https://leetcode.com/problems/reverse-integer/

> 原题描述：Given a 32-bit signed integer, reverse digits of an integer.

> 分析：将一个32bit的数进行翻转。首先想到%和/，求余10可以求解最后一位数，/10可以去掉最后一位数，那么就可以将一个数ABC分为AB、C，依次循环就可以获取每一位数字。而每获取一位数字m，就可以进行拼接res = res*10+m，达到翻转的目的。

- 代码实现
```Java
class Solution {
    public int reverse(int x) {
        int res = 0;
        int temp = 0;
        while(x!=0){
            temp=res;
            res = res*10+x%10;
            if(temp!=res/10){   //该判断用于处理int溢出
                return 0;
            }
            x=x/10;
        }
        return res;
    }
}
```
