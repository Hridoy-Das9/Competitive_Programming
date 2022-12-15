<h3>Problem:<a href="https://lightoj.com/problem/points-in-segments" > Points in segment </a> </h3>

```C++

#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define test      \
	ll t, cs = 1; \
	cin >> t;     \
	while (t--)
#define min3(a, b, c) min(a, min(b, c))
#define max3(a, b, c) max(a, max(b, c))
using namespace std;
#define rep(i, n) for (i = 0; i < n; i++)
#define rep2(i, m) for (i = 0; i < m; i++)
#define rep1(i, n) for (i = 1; i <= n; i++)
#define yes cout << "YES" << endl
#define no cout << "NO" << endl
#define nn << endl
#define sp ' '
#define MAX 10000009
#define all(v) v.begin(), v.end()
#define rall(v) v.rbegin(), v.rend()
#define print(v)           \
	for (auto it : v)      \
		cout << it << ' '; \
	cout << endl;
#define ff first
#define ss second
#define vvl vector<vector<ll>>
#define pll pair<ll, ll>
#define vll vector<ll>
#define vi vector<int>
#define vpll vector<pll>
#define vvi vector<vi>
#define nd &&
#define ub upper_bound
#define lb lower_bound
#define Cin(v)         \
	for (auto &it : v) \
		cin >> it;
#define take                \
	for (i = 0; i < n; i++) \
		cin >> v[i];

/// tmp.front()
/// tmp.pop_back()
/// tmp.erase(tmp.begin())
/// tmp.erase(--tmp.end())
/// digit count log10(n)+1
#define OK(a) cout << ((a) ? "YES" : "NO") << endl;
#define fio() ios_base::sync_with_stdio(false), cin.tie(NULL)
const int MOD = 1e9 + 7;
const int N = 1e6;
ll X[] = {+1, -1, 0, 0};
ll Y[] = {0, 0, -1, +1};
ll n, maxi;
vector<ll> prime;
bool vis[1000000];


int main()
{
	fio();
	test
	{
		ll n,m,k=0,j,d=0,i,ans=0;
		cin>>n>>m;
		vll v(n);
		for(i=0;i<n;i++)
		cin>>v[i];
		cout<<"Case "<<cs++<<':'<<endl;
		while(m--)
		{
			ll a,b;
			cin>>a>>b;
			ll l=lb(v.begin(),v.end(),a)-v.begin();
			ll r=ub(v.begin(),v.end(),b)-v.begin();
			cout<<r-l nn;

		}
	}
	return 0;
}
/*
1
2 2
1 1
0 1
 */
 
 
```
