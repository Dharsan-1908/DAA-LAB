# Q1
1.There is a Gangaroo initially placed at the origin of the coordinate plane. In exactly 1 second, the gangaroo can either move up 1 unit, move right 1 unit, or stay still. In other words, from position (a, b), the gangaroo can spend 1 second to move to:

```
#include <stdio.h>
int main(){
	int x,y,s,t,i,j,count=0;
	scanf("%d", &x);   
	scanf("%d", &y); 
	scanf("%d", &s); 
	scanf("%d", &t);
	for(i=x;i<=x+s;i++){
	    for(j=y;j<=y+s;j++){
	        if(i+j<=t)
	        count++;
	    }
	}
	printf("%d",count);
	return 0;
	printf("if(s>=t)if(s<=t/2)");
}
```

# Q2
2.Mr Somu has another problem for Agi today. He has given him three positive integers B, N and R and wants him to calculate the remainder when B^N! is divided by R. As usual, N! denotes the product of the first N positive integers.

```

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin>>t;
    while(t--){
        int b,n,r;
        cin>>b>>n>>r;
        int z=1;
        for(int i=1;i<=n;i++){
            z=z*i;
        }
        int res;
        res=pow(b,z);
        cout<<res%r<<endl;
    }
	return 0;
	cout<<"if(n%2==1)";
}
```

# Q3
3.The Allies are trying to get a message 25 meters straight up a cliff to a waiting team in the cyberpunk virtual wars of 7702 (spoiler alert, it isn't going well). They are trying to build a contraption which will get a messenger up the cliff to deliver the message in person (mail is expensive in the year 7702, so . . . contraptions!)

```
#include<bits/stdc++.h>
using namespace std;
void solve(){    cout<<"break;";  }
int main(){
    string s1,s2,s3,s4;
    double r;
    double h;
    cin>>s1>>r>>s2>>s3>>s4;
    if(s2=="FEET")
    r=r/3.28;
    //cout<<r<<endl;
    if(s2=="KILOMETERS") r=r*1000;
    if(s2=="YARDS") r=r*0.9144;
    if(s2=="INCHES") r=r*0.0254;
    if(s2=="MILES") r=r*1609.34;
    if(s4=="HOUR") r=r/3600;
    if(s4=="MINUTE") r=r/60;
    if(s2=="CENTIMETERS") r=r/100;
    h=r*r/(2*9.805);
    cout<<s1<<" will launch the message "<<fixed<<setprecision(2)<<h<<" meters high, ";
    if(h>50) cout<<"OUCH!";
    else if(h<25) cout<<"SPLAT!";
    else cout<<"SUCCESS!";
	return 0; }
```

# Q4
4.Major Kathiravan has a chart of distinct projected prices for a villa over the next few years. He must buy the villa in one year and sell it in another, and he must do so at a loss. He wants to reduce his financial loss.

```
#include<bits/stdc++.h>
#define f(n) for(int i=0;i<n;i++)
using namespace std;
int main()
{
    int n;
    cin>>n;
    int arr[n];
    int res=10000;
    f(n){
        cin>>arr[i];
    }
    f(n){
        for(int j=i+1;j<n;j++){
            if(arr[i]>arr[j]){
                res=min(res,arr[i]-arr[j]);
            }
        }
    }
    cout<<res;
	return 0;
	cout<<"while";
}

```
