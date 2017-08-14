### [题目链接](http://codeforces.com/problemset/problem/792/B)

#### <font color=blue>**题目意思**</font>
有n个人，序号从1~n，第一个人是领导人。现在给你一个k，接下来是k个数，代表k步。每走k步，最后走到的那个人淘汰，他的下一个人成为领导人。现在要你找出依次淘汰的人的序号。

#### <font color=blue>**解题思路**</font>
这就是一道简单的暴力题，用vector存储这n个人，然后走，将淘汰的人删除，接着继续走即可。

#### <font color=blue>**代码部分**</font>

```
#include <iostream>
#include <stdio.h>
#include <string.h>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    int n,k,a[150],t,p=0;
    vector <int> vec;
    memset(a,0,sizeof(a));
    cin>>n>>k;
    for(int i=1; i<=n; i++)
        vec.push_back(i);
    for(int i=1; i<=k; i++)
    {
        cin>>t;
        p=(p+t)%n;
        a[i]=vec[p];
        for(int j=p; j<n-1; j++)
            vec[j]=vec[j+1];
        vec.pop_back();
        n--;
    }
    for(int i=1; i<k; i++)
        cout<<a[i]<<" ";
    cout<<a[k]<<endl;
    return 0;
}

```

