# Q1
1.Devika is addicted to meat! Malik wants to keep her happy for n days. In order to be happy in i-th day, she needs to eat exactly ai kilograms of meat.
```
#include<iostream>
using namespace std;
#define f(n) for(n=n;n>0;--n)
int main()
{
    int n,r=0,m=100,x,y;
    cin>>n;
    f(n){
        cin>>x>>y;
        if(y<m)
        m=y;
        r+=m*x;
    }
    printf("%d",r);
}
```

#Q2
2.Nadanan's company employed n people. Now Nadanan needs to build a tree hierarchy of «supervisor-surbodinate» relations in the company (this is to say that each employee, except one, has exactly one supervisor). 	

```
#include<bits/stdc++.h>
using namespace std;
#define ans cin>>ans[0];cin>>a>>b>>c;
#define f(n) for(int i=0;i<n;i++)
void solve(){}
int main(){
    int n;cin>>n;
    int a[n];f(n) cin>>a[i];
    int M;cin>>M;
    map<int,int> m;
    while(M--){
        int x,y,c;cin>>x>>y>>c;
        if(m.find(y)==m.end())
            m[y]=c;
        else if(c<m[y]) 
            m[y]=c;
    }
    if((int)m.size()==n-1){
        long long int sum=0;
        for(auto j : m){
            sum+=j.second;
        }
        cout<<sum;
    }
    else cout<<-1;
}

```

# Q3
3.It's a very unfortunate day for Lavanya today. He got bad mark in algebra and was therefore forced to do some work in the kitchen, namely to cook borscht (traditional Russian soup). This should also improve his algebra skills

```
#include <bits/stdc++.h>
using namespace std;
#define res cin>>a[i],num+=a[i];
#define f1     for(int i=1;i<=n;i++)
double n,v,a[25],b[25],sum,mx=1e9;
int main(){
    cin>>n>>v;
    f1{
        cin>>a[i];
        sum+=a[i];
    }
    for(int i=1;i<=n;i++)
        cin>>b[i];
    for(int i=1;i<=n;i++)
        mx=min(mx,b[i]/a[i]); 
    cout << fixed<<setprecision(1)<<min(mx*sum,v);
    return 0;
}
```

# Q4
4.A stealing got into a matches warehouse and wants to steal as many matches as possible. 
```
#include<bits/stdc++.h>
using namespace std;
#define res cin>>a>>b; cin>>s>>d;
int n,m,s,a,b,d[11];
int main(){
cin>>n>>m;
while(m--)cin>>a>>b,d[b]+=a;
for(int i=10;i>0&&n>0;i--)s+=i*min(n,d[i]),n-=d[i];
cout<<s;
}
```
