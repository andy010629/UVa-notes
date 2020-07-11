# UVa 題目整理

## 10x
### UVa10041
```cpp=1
#include "bits/stdc++.h"
using namespace std;
main(){
	int kase;cin>>kase;
	while(kase--){
		int n;cin>>n;
		vector<int> vec(n);
		for(int &i:vec) cin>>i;
		sort(vec.begin(),vec.end());
		int mid = vec[vec.size()/2-1+vec.size()%2],sum=0;

		for(int i:vec)
			sum+= abs(mid-i);
		cout<<sum<<endl;
	}
}
```
---
---

## 11x
### UVa11321
```cpp=1
#include "bits/stdc++.h"
using namespace std;
int m,n;
bool cmp(int a,int b){
	if(a%m!=b%m){
		return (a%m)<(b%m);
	}
	else{
		if((a%2)&&!(b%2))
			return 1;		
		if(!(a%2)&&(b%2))
			return 0;
		if((a%2)&&(b%2))
			return a>b;
		if(!(a%2)&&!(b%2))
			return a<b;	
	}
}
main(){
	while(cin>>n>>m){
		cout<<n<<' '<<m<<endl;
		if(!n||!m) break;
		vector<int> vec(n);
		for(int& i:vec)
			cin>>i;
		sort(vec.begin(),vec.end(),cmp);
		for(int i:vec)
			cout<<i<<endl;
	}
}
```
