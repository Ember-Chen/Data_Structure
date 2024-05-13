---
title: KMP
date: 2024-05-13
categories: [总]
---

# 算法
1. 列表
    - 分别有"索引`j`", "字符串`s`", "`next[j]`", "`nextVal[j]`"这4行
2. 初始化表
    - `j`从1开始
    - `next[1]`固定为0, `next[2]` 固定为1
    - `nextVal[1]`固定为0
<!--more-->

# 例题
- [e.g.] `s=ababaaaba`

```pseudocode
j			1 2 3 4 5 6 7 8 9
s			a b a b a a a b a
next[j]			0 1 1 2 3 4 2 2 3
nextVal[j]		0 1 0 1 0 4 2 1 0

/* 固定操作：next[1]==0, next[2]==1, nextVal[1]==0 */

/* 求解next[i]的方式 (以求next[4]为例)
	1.index4之前的字符串：aba(index->123)
	2.字符串的最大头尾相同子串：a(index->1)
	3.子串a的下一个元素的下标：index->2
	4.因此next[4]==2;
*/

/* 求解nextVal[i]的方式
    e.g.求nextVal[3]
        1.next[3]==1
        2.s[3]==a, s[1]==a, 相等
        3.所以nextVal[3]=nextVal[1]
    e.g.求nextVal[6]
        1.next[6]==4
        2.s[6]==a, s[4]==b, 不相等
        3.所以nextVal[6]=next[6]
*/
```

- [e.g.] `s=aaaaaaaab`
```pseudocode
j			1 2 3 4 5 6 7 8 9
s			a a a a a a a a b
next[j]			0 1 2 3 4 5 6 7 8
nextVal[j]		0 0 0 0 0 0 0 0 8
```



