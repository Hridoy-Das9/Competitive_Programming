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
ll n, maxi;
vector<ll> prime;
vector<bool> vis;
vector<int> g[N];
void dfs(int rcv)
{
	vis[rcv]=1;
	for(auto it:g[rcv])
	{
		if(!vis[it])
		dfs(it);
	}
}
void solve()
{
	
	ll n, m, j, i, r, c, sm = 0;
	string s, p;
	cin >> n;
	cin >> s;
	n = n * 2;
 for(int i=0;i<=n;i++)g[i].clear();
        vis.assign(n+1,false);
	stack<pair<char, ll>> stk;
	for (i = 0; i < n; i++)
	{
		if (s[i] == '(')
		{
			stk.push({s[i], i});
		}
		else
		{
			int u = i;
			int v = stk.top().second;
			g[u].pb(v);
			g[v].pb(u);
			stk.pop();
		}
	}
	for (i = 0; i < n - 1; i++)
	{
		if (s[i] == ')' and s[i + 1] == '(')
		{
			g[i].pb(i + 1);
			g[i + 1].pb(i);
		}
	}
	for(i=0;i<n;i++)
	{
		if(!vis[i])
		{
			sm++;
			dfs(i);
		}
	}
	cout<<sm nn;
}
int main()
{
	fio();

	test
	{

		solve();
	}

	return 0;
}
/*
 */
```