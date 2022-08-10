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

#define LIM 100000

ll vis[LIM];
vector<vector<ll>> g;
vector<ll> lev, cnt;
ll n, m, l, x;
void inp()
{
    cin >> n;
    g.resize(n + 1);
    lev.resize(n + 1);
    cnt.resize(n + 1);
    for (ll i = 2; i <= n; i++)
    {
        ll p;
        cin >> p;
        g[p].push_back(i);
    }
    // cin >> x;
}

int dfs(ll u)
{
    cnt[u]=1;
    for (ll i = 0; i < g[u].size(); i++)
    {
        ll v = g[u][i];
        // lev[v] = lev[u] + 1;
        cnt[u]+=dfs(v);
        // cnt[u]+=cnt[v];
    }
    return cnt[u];
}
int main()
{
    lev.clear();
    cnt.clear();
    inp();
    memset(vis, 0, sizeof vis);
    
    lev[1] = 1;
    dfs(1);
    for(int i=1; i<=n; i++){
        cout<<i<<" "<<cnt[i]<<endl;
    }
    // for (ll u = 1; u <= n; u++)
    //     cnt[lev[u]]++;
    //     print(cnt);
    // cout << cnt[lev[x]] - 1 nn;
}

/*

*/
/*


*/
```