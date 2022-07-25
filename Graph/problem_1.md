<h3>Algorithm : DFS </h3>

```c++
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define test  \
	ll t,cs=1;     \
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
ll inf=10000007;
#define fio() ios_base::sync_with_stdio(false),cin.tie(NULL)
#define OK(a) cout << ((a) ? "YES" : "NO") << endl;

int X[]= {0,0,1,-1};
int Y[]= {1,-1,0,0};

const int MOD = 1e9 + 7;

# define LIM 100000

ll vis[LIM];
vector<vector<ll>>g;
vector<ll>col,par;
ll n,m,l,cnt=0;
void inp()
{
    cin>>n>>m;
    g.resize(n+1);
    col.resize(n+1);
    par.resize(n+1);
    for(ll i=0; i<m; i++)
    {
        ll u,v;
        cin>>u>>v;
        g[u].pb(v);
        g[v].pb(u);
    }
}

bool dfs(int u,int p)
{
    col[u]=1;
    par[u]=p;
    for(auto v:g[u])
    {
        if(v==par[u] )continue;
        if(col[v]) return true;
        if(dfs(v,u)) return true;
    }
    col[u]=2;
    return false;
}
int main()
{
    inp();
    memset(vis,0,sizeof vis);
    bool cycle=false;
    for(int u=1; u<=n; u++)
    {
        if(!col[u])
        {
            if(dfs(u,0))
            {
                cycle=true;
                break;
            }
        }
    }
    if(cycle==true)
        cout<<"The grapg is cycled" nn;
    else
        cout<<"The grapg is not cycled" nn;

}
```