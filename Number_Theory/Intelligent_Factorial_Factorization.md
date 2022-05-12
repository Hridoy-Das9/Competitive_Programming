<h3>Problem:<a href="https://lightoj.com/problem/intel-factor-factorization" > Intelligent Factorial Factorization </a> </h3>

```C++
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
ll inf=10007;
#define OK(a) cout << ((a) ? "YES" : "NO") << endl;
const int MOD = 1e9 + 7;
ll prime[10007];
vll v;
int main()
{
    ll k=1;
    test
    {
        vector<pair<ll,ll>>u;
        ll n;
        cin>>n;
        for(ll i=2; i*i<=inf; i++)
        {
            if(prime[i]==0)
            {
                //v.pb(i);
                for(ll j=i*i; j<=inf; j+=i)
                {
                    prime[j]=1;
                }
            }
        }
        for(ll i=2; i<=inf; i++)
        {
            if(prime[i]==0)
                v.pb(i);
        }
        // print(v) ;
        map<ll,ll>mp;
        ll cnt=0,m,d=0;
        for(ll j=2; j<=n; j++)
        {
            ll num=j;
            for(ll i=0; i<v.size() &&v[i]<=j; i++)
            {
                ll p=v[i];
                if(num%p==0)
                {
                    while(num%p==0)
                    {
                        num/=p;
                        mp[p]++;
                    }
                }
            }
        }

        cout<<"Case "<<k++<<": "<<n<<" = " ;
        for(auto it:mp)
            u.pb(it);
            cout<<u[0].first<<" ("<<u[0].second<<')';
            for(ll i=1;i<u.size();i++)
            {
                cout<<" * "<<u[i].first<<" ("<<u[i].second<<')';
            }
            cout<<endl;
        // cout<<it.first<<'('<<it.second <<')';
    }
}


```
