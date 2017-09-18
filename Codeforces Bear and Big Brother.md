### [题目链接](http://codeforces.com/problemset/problem/791/A)
### <font color=blue>**题目意思**</font>
现在有两头熊，分别为熊大，熊二。他们的体重分别为a，b，其中a<=b。熊大每年体重增加三倍，熊二每年体重增加两倍。现在问过几年熊大的体重比熊二重。

### <font color=blue>**解题思路**</font>
这就是一道简单的暴力题。我们每次比较增重后的体重是否符合a>b即可。具体过程看代码吧！

### <font color=blue>**代码部分**</font>

```
#include <iostream>
#include <stdio.h>
#include <string.h>
#include <algorithm>
using namespace std;
int main()
{
    int a,b,i;
    while(~scanf("%d%d",&a,&b))
    {
        i=0;
        while(a<=b)
        {
            i++;
            a*=3;
            b*=2;
        }
        cout<<i<<endl;
    }
    return 0;
}
```
