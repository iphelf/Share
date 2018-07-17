# ACM Template

[TOC]

## Binary Search

Description:

> Search for a special value in a monotone array very quickly with the help of the `_cmp()` function which returns positive number if the parameter is too big, negative if too small or zero if perfect.

Usage: 

```c++
int check(int x){return x-7;}
int sevenFirst=LowerBound(0,10,check);
int sevenLast=UpperBound(0,10,check);
```

Time: $$O(log_2 n)$$

```c++
int UpperBound(int x,int y,int (*_cmp)(int)){
    while(x<y){
        int m=ceil(x+(y-x)/2.0);
        if(_cmp(m)<=0) x=m;
        else y=m-1;
    }
    return y;
}
int LowerBound(int x,int y,int (*_cmp)(int)){
    while(x<y){
        int m=floor(x+(y-x)/2.0);
        if(_cmp(m)>=0) y=m;
        else x=m+1;
    }
    return x;
}
```
