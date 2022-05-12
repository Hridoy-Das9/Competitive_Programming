<h3>Problem: <a href="https://lightoj.com/problem/trailing-zeroes-i">Trailing Zeroes (I) </a></h3>

```c++
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define test  \
	ll t;     \
	cin >> t; \
	while (t--)
#define min3(a, b, c) min(a, min(b, c))
using namespace std;
#define rep(i, n) for (i = 0; i < n; i++)
#define rep2(i, m) for (i = 0; i < m; i++)
#define rep1(i, n) for (i = 1; i <= n; i++)
#define yes cout << "YES" << endl
#define no cout << "NO" << endl
#define nn << endl
#define sp << ' ' <<
#define MAX 10000009
#define all(v) v.begin(), v.end()
#define rall(v) v.rbegin(), v.rend()
#define print(v)           \
	for (auto it : v)      \
		cout << it << ' '; \
	cout << endl;
#define ff first
#define ss second
#define pll pair<ll, ll>
#define vll vector<ll>
#define vpll vector<pll>
#define nd &&
#define ub upper_bound
#define lb lower_bound
#define Cin(v)         \
	for (auto &it : v) \
		cin >> it;
///tmp.front()
///tmp.pop_back()
///tmp.erase(tmp.begin())
///tmp.erase(--tmp.end())
///digit count log10(n)+1
int inf=50000;
#define OK(a) cout << ((a) ? "YES" : "NO") << endl;
const int MOD = 1e9 + 7;
#define mk      make_pair
//v.pb(mk(a,b));
//double logg[1000005];
#define fio() ios_base::sync_with_stdio(false),cin.tie(NULL)
const ll N=1e6;
vector<ll> prime;
bool vis[1000000];

ll divCount(ll &n)
{
    ll ans=1;
    for(ll i=0; i<prime.size() && prime[i]*prime[i]<=n; i++)
    {
        if(n%prime[i]==0)
        {
            ll cnt=1;
            while(n%prime[i]==0)
            {
                cnt++;
                n/=prime[i];

            }
            //cout<<"cnt= "<<cnt nn;
            ans=ans*cnt;
             //
        }
    }
    if(n>1)
    {
        ans=ans*2;
    }
    return ans;
}

void sieve()
{
    for(ll i=3; i*i<=N; i+=2)
    {
        if(vis[i]==0)
        {
            for(ll j=i*i; j<=N; j+=2*i)
            {
                vis[j]=1;
            }
        }
    }
    prime.push_back(2);
    for(ll i=3; i<=N; i+=2)
    {
        if(vis[i]==0) prime.push_back(i);
    }

}
int main()
{
    fio();
    sieve();
    ll t,in=1;
    cin>>t;
    while(t--)
    {
        ll num,cnt=0,sq=0,f=0;
        cin>>num;
     //  divCount(num);
        cout<<"Case "<<in++<<": "<<divCount(num)-1 nn;

    }

}
```
