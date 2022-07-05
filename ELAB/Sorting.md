# Q1
1.RSA is a public key cryptosystem. Most important part of RSA is to choose two primes 'p' and 'q', and multiply them to construct an integer 'm'. You dont have to break RSA in this problem. Instead, given N, you have to find the number of integers less than equal to 'N' that are product of two primes. More formally, find |{p * q | p * q <= N, p, q are primes}|.

```
#include <bits/stdc++.h>
using namespace std;
void solve(){
    cout<<"break;";
}
bool isProduct(int num)
{
	int cnt = 0;
	for (int i = 2; cnt < 2 && i * i <= num; ++i) {
		while (num % i == 0) {
			num /= i;
			++cnt;
		}
	}
	if (num > 1)
		++cnt;
	return cnt == 2;
}
void findNumbers(int N)
{
	vector<int> vec;
	for (int i = 1; i <= N; i++) {
		if (isProduct(i) ) {
			vec.push_back(i);
		}
	}
	cout<<vec.size()<<endl;
}
int main()
{
    int t,N;
    cin>>t;
    while(t--){
        cin>>N;
        findNumbers(N);
    }
	return 0;
}
```

# Q2
2.The Sapphire Consulting and Marketing company is adding decorative pyramids to their corporate headquarters.

```
#include <stdio.h>
#include <stdlib.h>
int isqrt(n) int n; {
	int i;
	for(i=0;i*i<n;i++);
	return i;
}

int main() {
	int c;
	int t,h,s,i,j;
	int d;

	scanf("%d",&c);
	for(i=0;i<c;i++) {
		s=0;
		scanf("%d %d",&t,&h);
		d=isqrt(t); 
		s+=t+(d*4);

		for(j=1;j<h;j++) {
			s+=3; 
			s+=(d+j)*4; 
			if((d+j)>2)
				s+= (d+j-2)*2;
		}
		printf("%d liters\n",s);
	}
	return 0;
}
```

# Q3
3. The people of vadipatti have decided to paint each of their villas violet, grey, or blue. They've also decided that no two neighboring villas will be painted the same color. The neighbors of villa i are villas i-1 and i+1. The first and last villas are not neighbors.

```
#include<bits/stdc++.h>
using namespace std;
#define fainou ios_base::sync_with_stdio(false);cin.tie(NULL)
#define ll long long
#define mod 1000000007
void solve(){
    cout<<"for(i=0;i<tc;i++) for(j=0;j<N;j++)for(j=1;j<N;j++)";
}
int main(){
	fainou;
	ll t;
	cin>>t;
	int i=1;
	while(t--){
	    ll n;
		cin>>n;
		ll a[n][3],ans;
		cin>>a[0][0]>>a[0][1]>>a[0][2];
		for(ll i=1;i<n;i++){
			cin>>a[i][0]>>a[i][1]>>a[i][2];
			a[i][0]+=min(a[i-1][1],a[i-1][2]);
			a[i][1]+=min(a[i-1][0],a[i-1][2]);
			a[i][2]+=min(a[i-1][0],a[i-1][1]);
		}
		ans=min(a[n-1][0],a[n-1][1]);
		ans=min(a[n-1][2],ans);
		cout<<"Line "<<i++<<": "<<ans<<"\n";
	}
}
```

# Q4
4.	Great news! You get to go to Japan on a class trip! Bad news, you don't know how to use the Yen which is the name of the Japanese cash system.

```
#include<iostream>
using namespace std;
int main()
{
    int items;
    int a,j,cnt=0;
    cin>>a>>items;
    int c[items];
    string s[items];
    for(j=0;j<items;j++){
        cin>>s[j]>>c[j];
        if(c[j]<a){
            cout<<"I can afford "<<s[j]<<endl;
            a=a-c[j];
        }
        else{
            cnt++;
        cout<<"I can't afford "<<s[j]<<endl;
        }
        //cout<<cnt;
    }
    if(cnt==items)
    cout<<"I need more Yen!";
    else
    cout<<a;
	return 0;
	cout<<"for(i=1;i<=yen;i++) int i,j;";
}
```
