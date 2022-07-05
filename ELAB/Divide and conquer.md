# Q1
1.Leopard is in the Amusement Park. And now she is in a queue in front of the Ferris wheel. There are n people (or Leopard more precisely) in the queue: we use first people to refer one at the head of the queue, and n-th people to refer the last one in the queue.

```
#include<cstdio>
#include<iostream>
using namespace std;
inline int getint(){
char c;
while((c=getchar())<'0'||c>'9');
return c-'0';
}
const int N=4005,inf=.5e9;
int n,k,sum[N][N],f[N],g[N];
int main(){
cin>>n>>k;
for(int i=1;i<=n;i++)
for(int j=1;j<=n;j++)
sum[i][j]=sum[i-1][j]+sum[i][j-1]-sum[i-1][j-1]+getint();
g[n+1]=n;
for(int kk=2;kk<=k;kk++)
for(int i=n;i;i--){
f[i]=-inf;
for(int j=g[i];j<=g[i+1]&&j<i;j++){
int now=f[j]-sum[j][j]+sum[j][i];
if(now>f[i]){
f[i]=now;
g[i]=j;
}
}
}
printf("%d\n",sum[n][n]/2-f[n]);
}
```

# Q2
2.Neeraj definition a string is said to be a palindrome if it does change when get reversed. 13131 is a nice example of a palindrome.

```
#include<bits/stdc++.h>
using namespace std;
void garbage(){
    cout<<"int go(int f,int s)vcin>>a; ";
}
int findMinInsertions(string str, int l, int h)
{
    if (l > h) return INT_MAX;
    if (l == h) return 0;
    if (l == h - 1) return (str[l] == str[h])? 0 : 1;
    return (str[l] == str[h])?
                    findMinInsertions(str, l + 1, h - 1):
                    (min(findMinInsertions(str, l, h - 1),
                    findMinInsertions(str, l + 1, h)) + 1);
}
int main()
{
    string s;
    cin>>s;
    cout << findMinInsertions(s, 0, s.length() - 1);
    return 0;
}
```

# Q3
3.Lakshman and Sukran are the best competitive programmers in their town. However, they can't both qualify to an important contest. The selection will be made with the help of a single problem. Bhoominath, a friend of Lakshman, managed to get hold of the problem before the contest. Because he wants to make sure Lakshman will be the one qualified, he tells Lakshman the following task.
```
#include <bits/stdc++.h>
using namespace std;
long long n, i = 1, j, k = 9e9, x, s[100001], d;
 
int main() {
    cin>>n;
    for (; i <= n; i++){ cin>>x;s[i] = s[i - 1] + x;}
    for (i = 1; i <= n; i++)
        for (j = max(1ll, i - 20000); j <= i; j++)
            if (i != j) k = min(k, (i - j) * (i - j) + (s[i] - s[j]) * (s[i] - s[j]));
    cout << k;
}

```

# Q4
4.Let P be an array consisting of N numbers. The array's elements are numbered from 1 to N, even is an array consisting of the numerals whose numbers are even in P (eveni = P2i, 1 ≤ 2i ≤ n), odd is an array consisting of the numerals whose numbers are odd in а (oddi = P2i - 1, 1 ≤ 2i - 1 ≤ n). Then let's define the transformation of array F(P) in the following manner:

```
#include <stdio.h>

int md;

int s(int n) {
    return (n % 2 == 0 ? (n / 2 % md) * ((n + 1) % md) : (n % md) * ((n + 1) / 2 % md)) % md;
}

int sum, cnt;

void queries(long long n, long long k, long long a) {
    int sum0, cnt0, sum1, cnt1;

    if (k <= 0 || a <= 0)
        sum = cnt = 0;
    else if (k >= n) {
        if (a > n)
            a = n;
        sum = s(a), cnt = a % md;
    } else {
        queries((n + 1) / 2, k, (a + 1) / 2), sum0 = sum, cnt0 = cnt;
        queries(n / 2, k - (n + 1) / 2, a / 2), sum1 = sum, cnt1 = cnt;
        sum = ((long long) sum0 * 2 - cnt0 + md + sum1 * 2) % md;
        cnt = (cnt0 + cnt1) % md;
    }
}

int main() {
    int n;
    int m;

    scanf("%d%d%d",&n,&m,&md);
    while (m--) {
        long long l, r, a, b;
        int ans;

        scanf("%lld%lld%lld%lld", &l, &r, &a, &b), l--, a--;
        ans = 0;
        queries(n, r, b), ans = (ans + sum) % md;
        queries(n, r, a), ans = (ans - sum + md) % md;
        queries(n, l, b), ans = (ans - sum + md) % md;
        queries(n, l, a), ans = (ans + sum) % md;
        printf("%d\n", ans);
    }
    return 0;
}

```
