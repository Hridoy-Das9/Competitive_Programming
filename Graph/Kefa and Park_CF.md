```cpp

Codeforces Round #321 (Div. 2)--->C number

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
const int N = 1e6 + 5;
int dp[N];
ll X[] = {+1, -1, 0, 0};
ll Y[] = {0, 0, -1, +1};
int i, j,ans=0, x, y, n, m;
vector<string> s;
vi vis,cat;
vvi v;
void inp()
{
   
    int i;
    cin>>n>>m;
    v.resize(n+1);
    cat.resize(n+1);vis.resize(n+1,0);
    for(i=1;i<=n;i++)
    {
        cin>>cat[i];
    }
    for(i=0;i<n-1;i++)
    {
        cin>>x>>y;
        v[x].pb(y);
        v[y].pb(x);
    }

}
void dfs(int node,int cnt)
{
//cout<<"prnt="<<node<<' '<<cnt nn;

    vis[node]=1;
    if(cat[node])
    cnt++;
    else
    cnt=0;
    if(cnt>m)
    return;
    if(v[node].size()==1 and node!=1)
    ans++;
    
    for(int i=0;i<v[node].size();i++)
    {
        if(!vis[v[node][i]])
        {
            dfs(v[node][i],cnt);
        }
    }
}
int main()
{
     inp();
     dfs(1,0);

cout<<ans nn;
}


```
