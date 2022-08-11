```cpp
#include <bits/stdc++.h>
#define ll long long
#define pb push_back
#define test      \
    ll t, cs = 1; \
    cin >> t;     \
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
/// tmp.front()
/// tmp.pop_back()
/// tmp.erase(tmp.begin())
/// tmp.erase(--tmp.end())
/// digit count log10(n)+1
ll inf = 10000007;
#define fio() ios_base::sync_with_stdio(false), cin.tie(NULL)
#define OK(a) cout << ((a) ? "YES" : "NO") << endl;

int X[] = {0, 0, 1, -1};
int Y[] = {1, -1, 0, 0};

const int MOD = 1e9 + 7;

#define LIM 20005

vll vis(LIM);
vector<vector<ll>> g;
vector<ll> lev, cnt, col;
ll n, m, l, x;
map<ll, ll> mp;
const int SiZe = 20025;
void inp()
{
    g.clear();

        col.clear();
        vis.clear();
    cin >> n;
    g.resize(SiZe);
    col.resize(SiZe);
    vis.resize(SiZe,0);
    for (ll i = 0; i < n; i++)
    {
        ll u, v;
        cin >> u >> v;
        g[u].push_back(v);
        g[v].push_back(u);
    }
}

bool dfs(ll u, ll c)
{
    vis[u] = 1;
    col[u] = c;
    mp[c]++;
    for (ll i = 0; i < g[u].size(); i++)
    {
        ll v = g[u][i];
        if (col[u] == col[v])
            return false;
        if (vis[v])
            continue;
        if (!dfs(v, 3 - c))
            return false;
    }
    return true;
}
int main()
{
    ll k=1;
    test
    {
        inp();
        bool bicol = true;
        int ans=0;
        for (ll i = 1; i <=20000; i++)
        {
            if (!vis[i] && g[i].size()>0)
            {
                mp.clear();
                dfs(i, 1);
                ans += max(mp[1],mp[2]);
                
            }
        }
        cout<<"Case "<<k++<<": "<<ans nn;
    }
}

/*

*/
/*


*/
```