> An oier

我的账号
-
- [ATCODER](https://atcoder.jp/users/valerain)
- [Codeforces](https://codeforces.com/profile/_Ryuga_Pro)

著名比赛历年真题 CSP-J/S USACO 铜/金 省选 NOIP NOI CTT WC IOI
-
[著名比赛历年真题 CSP/J USACO 铜](https://www.luogu.com.cn/training/914825)

[著名比赛历年真题 CSP-S USACO 金](https://www.luogu.com.cn/training/914849)

[著名比赛历年真题 省选 NOIP](https://www.luogu.com.cn/training/914862)

[著名比赛历年真题 NOI CTT](https://www.luogu.com.cn/training/914889)

[著名比赛历年真题 WC IOI](https://www.luogu.com.cn/training/914898)

### 人生大事
$2025/11/27$ 红橙黄绿蓝紫黑 200 祭 [P9973 [THUPC 2024 初赛] 你说得对，但是 AIGC](https://www.luogu.com.cn/problem/P9973)

### 有趣的网站
[OI教练模拟器](https://qoj.ac/files/OItrainer-main/start.html)

快读模版
```cpp
namespace FastIO{
	const int Size=1<<21;
	char ibuf[Size],obuf[Size],*p1=ibuf,*p2=ibuf,*p3=obuf;
	#define getchar() (p1==p2&&(p2=(p1=ibuf)+fread(ibuf,1,Size,stdin),p1==p2)?EOF:*p1++)
	#define putchar(x) (p3-obuf<Size?(*p3++=(x)):(fwrite(obuf,1,p3-obuf,stdout),p3=obuf,*p3++=(x)))
	inline void flush(){if(p3>obuf) fwrite(obuf,1,p3-obuf,stdout),p3=obuf;}
	template<class T>
	T read(T&x){
		x=0;bool f=false;char ch=getchar();
		while(!isdigit(ch)) f|=!(ch^'-'),ch=getchar();
		while(isdigit(ch)) x=(x<<1)+(x<<3)+(ch&0xF),ch=getchar();
		x=(f?-x:x);return x;
	}template<class T>
	int reads(T*s){
		char ch=getchar();int len=0;
		while(ch==' '||ch=='\n'||ch=='\r') ch=getchar();
		while(ch!=' '&&ch!='\n'&&ch!=EOF&&ch!='\r') s[len++]=ch,ch=getchar();
		s[len]='\0';return len;
	}template<class T>
	T readd(T&x){
		x=0;bool f=false;char ch=getchar();
		while(!isdigit(ch)) f|=!(ch^'-'),ch=getchar();
		while(isdigit(ch)) x=x*10+(ch&0xF),ch=getchar();
		if(ch=='.'){ch=getchar();T d=1;while(isdigit(ch)) d*=0.1,x+=d*(ch&0xF),ch=getchar();}
		x=(f?-x:x);return x;
	}template<class T>
	void write(T x,char ch=' '){
		if(x<0) putchar('-'),x=-x;
		char tmp[41];int cnt=0;
		while(x>9) tmp[cnt++]=x%10+'0',x/=10;tmp[cnt++]=x+'0';
		while(cnt) putchar(tmp[--cnt]);putchar(ch);
	}template<class T>
	void writes(T x,int l=0,int r=-1){
		if(~r){for(int i=l;i<=r;i++) putchar(x[i]);}
		else{for(int i=l;x[i];i++) putchar(x[i]);}
	}template<class T>
	void writed(T x,int p=6,char ch=' '){
		if(x<0) putchar('-'),x=-x;
		T d=0.5;for(int i=0;i<p;i++) d*=0.1;x+=d;
		i128 g=(i128)(x);p?write(g,'.'):write(g,ch);
		if(p){T f=x-g;for(int i=0,d;i<p;i++) f*=10,d=(int)(f),putchar(d+'0'),f-=d;putchar(ch);}
	}
}
using namespace FastIO;
```
记得加`flush();`

一些常见的类型
```cpp
using ll = long long;
using ull = unsigned long long;
using uint = unsigned int;
using ld = long double;
using cd = complex<double>;
```
一些常见宏
```cpp
#define i128  __int128
#define fir first
#define sec second
#define pii pair<int, int>
#define pll pair<ll, ll>
#define ls(x) (x << 1)
#define rs(x) (x << 1 | 1)
#define lowbit(x) (x & -x)
#define AC return 0
```
一些常量
```cpp
const int dx[] = {-1, 1, 0, 0};
const int dy[] = {0, 0, -1, 1};
const int dx8[] = {-1, 1, 0, 0, -1, -1, 1, 1};
const int dy8[] = {0, 0, -1, 1, -1, 1, -1, 1};
const int MOD1 = 1e9 + 7;
const int MOD = 998244353;
const double PI = acos(-1);
```
一些函数
```cpp
ll qpow(ll a,ll b,ll mod=MOD){ll res=1;while(b){if(b&1)res=res*a%mod;a=a*a%mod;b>>=1;}return res;}

```
```cpp
ll qmul(ll a,ll b,ll mod=MOD){ll res=0;while(b){if(b&1)res=(res+a)%mod;a=(a+a)%mod;b>>=1;}return res;}

```
```cpp
ll range_sum(const vector<ll>&pre,int l,int r){return pre[r+1]-pre[l];}

```
```cpp
vector<int>linear_sieve(int n){vector<int>primes;vector<bool>is_prime(n+1,true);for(int i=2;i<=n;i++){if(is_prime[i])primes.push_back(i);for(int p:primes){if(i*p>n)break;is_prime[i*p]=false;if(i%p==0)break;}}return primes;}

```
很厉害的排序
```cpp
void counting_sort(vector<int>&arr){if(arr.empty())return;int max_val=*max_element(arr.begin(),arr.end());int min_val=*min_element(arr.begin(),arr.end());long long range=(long long)max_val-min_val+1;if(range>10000000){sort(arr.begin(),arr.end());return;}if(range*sizeof(int)>256*1024*1024){sort(arr.begin(),arr.end());return;}vector<int>count(range,0);vector<int>output(arr.size());for(int x:arr){count[x-min_val]++;}for(int i=1;i<range;i++){count[i]+=count[i-1];}for(int i=arr.size()-1;i>=0;i--){int pos=arr[i]-min_val;output[count[pos]-1]=arr[i];count[pos]--;}arr=output;}

```
```cpp
void LL_counting_sort(vector<long long>&arr){if(arr.empty())return;long long max_val=*max_element(arr.begin(),arr.end());long long min_val=*min_element(arr.begin(),arr.end());long long range=max_val-min_val+1;if(range>10000000){sort(arr.begin(),arr.end());return;}if(range*sizeof(long long)>256*1024*1024){sort(arr.begin(),arr.end());return;}vector<long long>count(range,0);vector<long long>output(arr.size());for(long long x:arr){count[x-min_val]++;}for(long long i=1;i<range;i++){count[i]+=count[i-1];}for(long long i=arr.size()-1;i>=0;i--){long long pos=arr[i]-min_val;output[count[pos]-1]=arr[i];count[pos]--;}arr=output;}

```

最后火车头
```cpp
#include <bits/stdc++.h>
using namespace std;
using ll = long long;
using ull = unsigned long long;
using uint = unsigned int;
using ld = long double;
using cd = complex<double>;
#define i128  __int128
#define fir first
#define sec second
#define pii pair<int, int>
#define pll pair<ll, ll>
#define ls(x) (x << 1)
#define rs(x) (x << 1 | 1)
#define lowbit(x) (x & -x)
#define AC return 0
const int dx[] = {-1, 1, 0, 0};
const int dy[] = {0, 0, -1, 1};
const int dx8[] = {-1, 1, 0, 0, -1, -1, 1, 1};
const int dy8[] = {0, 0, -1, 1, -1, 1, -1, 1};
const int MOD1 = 1e9 + 7;
const int MOD = 998244353;
const double PI = acos(-1);
namespace FastIO{
	const int Size=1<<21;
	char ibuf[Size],obuf[Size],*p1=ibuf,*p2=ibuf,*p3=obuf;
	#define getchar() (p1==p2&&(p2=(p1=ibuf)+fread(ibuf,1,Size,stdin),p1==p2)?EOF:*p1++)
	#define putchar(x) (p3-obuf<Size?(*p3++=(x)):(fwrite(obuf,1,p3-obuf,stdout),p3=obuf,*p3++=(x)))
	inline void flush(){if(p3>obuf) fwrite(obuf,1,p3-obuf,stdout),p3=obuf;}
	template<class T>
	T read(T&x){
		x=0;bool f=false;char ch=getchar();
		while(!isdigit(ch)) f|=!(ch^'-'),ch=getchar();
		while(isdigit(ch)) x=(x<<1)+(x<<3)+(ch&0xF),ch=getchar();
		x=(f?-x:x);return x;
	}template<class T>
	int reads(T*s){
		char ch=getchar();int len=0;
		while(ch==' '||ch=='\n'||ch=='\r') ch=getchar();
		while(ch!=' '&&ch!='\n'&&ch!=EOF&&ch!='\r') s[len++]=ch,ch=getchar();
		s[len]='\0';return len;
	}template<class T>
	T readd(T&x){
		x=0;bool f=false;char ch=getchar();
		while(!isdigit(ch)) f|=!(ch^'-'),ch=getchar();
		while(isdigit(ch)) x=x*10+(ch&0xF),ch=getchar();
		if(ch=='.'){ch=getchar();T d=1;while(isdigit(ch)) d*=0.1,x+=d*(ch&0xF),ch=getchar();}
		x=(f?-x:x);return x;
	}template<class T>
	void write(T x,char ch=' '){
		if(x<0) putchar('-'),x=-x;
		char tmp[41];int cnt=0;
		while(x>9) tmp[cnt++]=x%10+'0',x/=10;tmp[cnt++]=x+'0';
		while(cnt) putchar(tmp[--cnt]);putchar(ch);
	}template<class T>
	void writes(T x,int l=0,int r=-1){
		if(~r){for(int i=l;i<=r;i++) putchar(x[i]);}
		else{for(int i=l;x[i];i++) putchar(x[i]);}
	}template<class T>
	void writed(T x,int p=6,char ch=' '){
		if(x<0) putchar('-'),x=-x;
		T d=0.5;for(int i=0;i<p;i++) d*=0.1;x+=d;
		i128 g=(i128)(x);p?write(g,'.'):write(g,ch);
		if(p){T f=x-g;for(int i=0,d;i<p;i++) f*=10,d=(int)(f),putchar(d+'0'),f-=d;putchar(ch);}
	}
}
using namespace FastIO;
void freop(){freopen(".in","r",stdin);freopen(".out","w",stdout);}
ll qpow(ll a,ll b,ll mod=MOD){ll res=1;while(b){if(b&1)res=res*a%mod;a=a*a%mod;b>>=1;}return res;}
ll qmul(ll a,ll b,ll mod=MOD){ll res=0;while(b){if(b&1)res=(res+a)%mod;a=(a+a)%mod;b>>=1;}return res;}
ll range_sum(const vector<ll>&pre,int l,int r){return pre[r+1]-pre[l];}
vector<int>linear_sieve(int n){vector<int>primes;vector<bool>is_prime(n+1,true);for(int i=2;i<=n;i++){if(is_prime[i])primes.push_back(i);for(int p:primes){if(i*p>n)break;is_prime[i*p]=false;if(i%p==0)break;}}return primes;}
void counting_sort(vector<int>&arr){if(arr.empty())return;int max_val=*max_element(arr.begin(),arr.end());int min_val=*min_element(arr.begin(),arr.end());long long range=(long long)max_val-min_val+1;if(range>10000000){sort(arr.begin(),arr.end());return;}if(range*sizeof(int)>256*1024*1024){sort(arr.begin(),arr.end());return;}vector<int>count(range,0);vector<int>output(arr.size());for(int x:arr){count[x-min_val]++;}for(int i=1;i<range;i++){count[i]+=count[i-1];}for(int i=arr.size()-1;i>=0;i--){int pos=arr[i]-min_val;output[count[pos]-1]=arr[i];count[pos]--;}arr=output;}
void LL_counting_sort(vector<long long>&arr){if(arr.empty())return;long long max_val=*max_element(arr.begin(),arr.end());long long min_val=*min_element(arr.begin(),arr.end());long long range=max_val-min_val+1;if(range>10000000){sort(arr.begin(),arr.end());return;}if(range*sizeof(long long)>256*1024*1024){sort(arr.begin(),arr.end());return;}vector<long long>count(range,0);vector<long long>output(arr.size());for(long long x:arr){count[x-min_val]++;}for(long long i=1;i<range;i++){count[i]+=count[i-1];}for(long long i=arr.size()-1;i>=0;i--){long long pos=arr[i]-min_val;output[count[pos]-1]=arr[i];count[pos]--;}arr=output;}

void solve(){

}
int main()
{
   	solve();
	flush();
    AC;
}
```

如果你喜欢打`CF`或`AT`

```cpp
#include <bits/stdc++.h>
using namespace std;
using ll=long long;
void solve(){
	
}
int main()
{
   	solve();
    return 0;
}

```
