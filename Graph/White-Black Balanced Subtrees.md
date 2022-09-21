```c++
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
#define pii  pair<int, int>
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
ll n, cnt=0,maxi;
vector<ll> prime;
vector<bool> vis;
vvi g;
string s;
pii dfs(int node,int par)
{
	int blk=(s[node-1]=='B')?1:0;
	int wht=1-blk;
	//  for(auto it:g[node]){
    //     if(par==it)continue;
    //     pii tmp = dfs(it,node);
    //     blk+=tmp.ff;
    //     wht+=tmp.ss;
    // }
	for(auto it:g[node])
	{
		if(it!=par)
		{
				pii tmp=dfs(it,node);
			blk+=tmp.ff;
			wht+=tmp.ss;
		}	
	}
	if(blk==wht)
		cnt++;
		return make_pair(blk,wht);
}
int main()
{
	fio();
	test
	{
		ll n,i;
		cin>>n;
		g.clear();
		g.resize(n+1);
		for(i=2;i<=n;i++)
		{
			ll x;
			cin>>x;
			g[x].pb(i);
			g[i].pb(x);
		}
		cin>>s;
		cnt=0;
		dfs(1,0);
		cout<<cnt nn;
	}

	return 0;
}
/*
 */
```