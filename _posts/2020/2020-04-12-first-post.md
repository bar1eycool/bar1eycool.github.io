---
layout:     post
title:      "Welcome to Jekyll!"
author:     hs1n
categories: [programming]
tags:       ["Mark and Toys", "Greedy Florist"]
date:       2020-04-12 18:00:00 +0800
excerpt_separator: <!--more-->
---

**Hello world**, 第一篇 Jekyll 還不知道該寫些甚麼，先貼一些今天寫的hackerrank題目。
<!--more-->

## Mark and Toys <font size="1" color="orange">Medium</font>
不得不吐槽一下Testcase，Mark還真有錢...
### C# code
``` csharp
public int maximumToys (int[] prices, int k) {
    int change = k;
    int count = 0;
    
    Array.Sort (prices);

    for (int i = 0; i < prices.Length; i++) {
        if (change - prices[i] > 0 && ((prices[i] <= (1000000000)) && (prices[i] >= 1))) {
            change -= prices[i];
            count++;
        }
    }
    return count;
}
```

## Greedy Florist <font size="1" color="orange">Medium</font>

### C# code
``` csharp
 public int getMinimumCost (int k, int[] c) {
     int flowerCount = c.Length;
     int total = 0;

     if (k >= flowerCount) {
         total = c.Sum ();
         return total;
     } else {
         Array.Sort (c);
         Array.Reverse (c);
         int extraFee = 1;
         int normalPriceCount = k;
         for (int i = 0; i < c.Length; i++) {
             if (normalPriceCount > 0) {
                 total += c[i];
                 normalPriceCount--;
             } else {
                 total += (extraFee + 1) * c[i];

                 if ((k - i - 1) % k == 0) {
                     extraFee += 1;
                 }
             }
         }
     }
     return total;
 }
```