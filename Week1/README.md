class Solution {
public:
int evalRPN(vector<string>& tokens) {
stack<int> operands;
for(int i=0;i<tokens.size();i++){
if(tokens[i]=="+"){
int op1=operands.top();
operands.pop();
int op2=operands.top();
operands.pop();
operands.push(op1+op2);
continue;
}
if(tokens[i]=="/"){
int op1=operands.top();
operands.pop();
int op2=operands.top();
operands.pop();
operands.push(op2/op1);
continue;
}
if(tokens[i]=="-"){
int op1=operands.top();
operands.pop();
int op2=operands.top();
operands.pop();
operands.push(op2-op1);
continue;
}
if(tokens[i]=="*"){
int op1=operands.top();
operands.pop();
int op2=operands.top();
operands.pop();
operands.push(op1*op2);
continue;
}
operands.push(stoi(tokens[i]));
}
return operands.top();
}
};

############################################################################################

#define gc getchar_unlocked
#define fo(i, n) for (i = 0; i < n; i++)
#define Fo(i, k, n) for (i = k; k < n ? i < n : i > n; k < n ? i += 1 : i -= 1)
#define debv(x) for(i=0;i<x.size();i++) cout<<x[i]<<" "
#define ll long long
#define si(x) scanf("%d", &x)
#define sl(x) scanf("%lld", &x)
#define ss(s) scanf("%s", s)
#define pi(x) printf("%d\n", x)
#define pl(x) printf("%lld\n", x)
#define ps(s) printf("%s\n", s)
#define deb(x) cout << #x << "=" << x << endl
#define deb2(x, y) cout << #x << "=" << x << "," << #y << "=" << y << endl
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(x) x.begin(), x.end()
#define clr(x) memset(x, 0, sizeof(x))
#define sortall(x) sort(all(x))
#define tr(it, a) for (auto it = a.begin(); it != a.end(); it++)
#define PI 3.1415926535897932384626
typedef pair<int, int> pii;
typedef pair<ll, ll> pll;
typedef vector<int> vi;
typedef vector<ll> vl;
typedef vector<pii> vpii;
typedef vector<vi> vvi;
typedef vector<vl> vvl;
const int mod = 1000000007;
class Solution {
public:

    void helper(vector<vector<int>> &ans , vector<int> &curr , int ix , int k, int n, int sum){
        int s=curr.size(),i;
        if(sum==n && s==k){
            ans.pb(curr);
        }
        if(s<k){
            Fo(i,ix,10){
                if(sum+i<=n){
                    curr.pb(i);
                    helper(ans,curr,i+1,k,n,sum+i);
                }else{
                    break;
                }
            }
        }
        if(curr.size()>=1){
            curr.pop_back();
        }

    }
    vector<vector<int>> combinationSum3(int k, int n) {
        vector<vector<int>> ans;
        vector<int> curr;
        helper(ans,curr,1,k,n,0);
        return ans;


    }

};

############################################################################################

#define gc getchar_unlocked
#define fo(i, n) for (i = 0; i < n; i++)
#define Fo(i, k, n) for (i = k; k < n ? i < n : i > n; k < n ? i += 1 : i -= 1)
#define debv(x) for(i=0;i<x.size();i++) cout<<x[i]<<" "
#define ll long long
#define si(x) scanf("%d", &x)
#define sl(x) scanf("%lld", &x)
#define ss(s) scanf("%s", s)
#define pi(x) printf("%d\n", x)
#define pl(x) printf("%lld\n", x)
#define ps(s) printf("%s\n", s)
#define deb(x) cout << #x << "=" << x << endl
#define deb2(x, y) cout << #x << "=" << x << "," << #y << "=" << y << endl
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(x) x.begin(), x.end()
#define clr(x) memset(x, 0, sizeof(x))
#define sortall(x) sort(all(x))
#define tr(it, a) for (auto it = a.begin(); it != a.end(); it++)
#define PI 3.1415926535897932384626
typedef pair<int, int> pii;
typedef pair<ll, ll> pll;
typedef vector<int> vi;
typedef vector<ll> vl;
typedef vector<pii> vpii;
typedef vector<vi> vvi;
typedef vector<vl> vvl;
class Solution {
public:
string getHint(string secret, string guess) {
int i,j,k,b=0,c=0;

        unordered_map<char,int> sec,gues;
        fo(i,secret.size()){
            bool g=true,s=true;
            if(secret[i]==guess[i]){
                b++;
                continue;
            }
            if(sec[guess[i]]>=1){
                c++;
                sec[guess[i]]--;
                g=false;

            }
            if(gues[secret[i]]>=1){
                c++;
                gues[secret[i]]--;
                s=false;

            }
            if(s){
                sec[secret[i]]++;
            }
            if(g){
                 gues[guess[i]]++;
            }



        }
        string ans= to_string(b) + "A" +   to_string(c) + "B";
        return ans;

    }

};

############################################################################################

#define gc getchar_unlocked
#define fo(i, n) for (i = 0; i < n; i++)
#define Fo(i, k, n) for (i = k; k < n ? i < n : i > n; k < n ? i += 1 : i -= 1)
#define debv(x) for(i=0;i<x.size();i++) cout<<x[i]<<" "
#define ll long long
#define si(x) scanf("%d", &x)
#define sl(x) scanf("%lld", &x)
#define ss(s) scanf("%s", s)
#define pi(x) printf("%d\n", x)
#define pl(x) printf("%lld\n", x)
#define ps(s) printf("%s\n", s)
#define deb(x) cout << #x << "=" << x << endl
#define deb2(x, y) cout << #x << "=" << x << "," << #y << "=" << y << endl
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(x) x.begin(), x.end()
#define clr(x) memset(x, 0, sizeof(x))
#define sortall(x) sort(all(x))
#define tr(it, a) for (auto it = a.begin(); it != a.end(); it++)
#define PI 3.1415926535897932384626
typedef pair<int, int> pii;
typedef pair<ll, ll> pll;
typedef vector<int> vi;
typedef vector<ll> vl;
typedef vector<pii> vpii;
typedef vector<vi> vvi;
typedef vector<vl> vvl;
const int mod = 1000000007;
class Solution {
public:
int maxRotateFunction(vector<int>& nums) {
int i,j,k,n=nums.size(),cum_sum=0;
// vvi multiples(n,vector<int>(n));
// fo(i,nums.size()){
// fo(j,nums.size()){
// multiples[i][j]=nums[i] * j;
// }
// }
// int cum_sum=0,ans=0;
// fo(j,n){
// int k=j;
// cum_sum=0;
// fo(i,n){
// cum_sum+=multiples[i][k%n];
// k++;
// }
// ans=max(ans,cum_sum);
// }
// return ans;
int ans=0,sum=0;
fo(i,n){
cum_sum+=nums[i];
ans+=nums[i]*i;
}
int li=n-1;
sum=ans;
Fo(i,1,n){
sum=sum + cum_sum - n\*nums[li];
//deb(sum);
li--;
ans=max(ans,sum);
}
return ans;
}

};

############################################################################################

//Largest Divisible Subset

#include <bits/stdc++.h>
using namespace std;
#define gc getchar_unlocked
#define fo(i, n) for (i = 0; i < n; i++)
#define Fo(i, k, n) for (i = k; k < n ? i < n : i > n; k < n ? i += 1 : i -= 1)
#define debv(x) for(i=0;i<x.size();i++) cout<<x[i]<<" "
#define ll long long
#define si(x) scanf("%d", &x)
#define sl(x) scanf("%lld", &x)
#define ss(s) scanf("%s", s)
#define pi(x) printf("%d\n", x)
#define pl(x) printf("%lld\n", x)
#define ps(s) printf("%s\n", s)
#define deb(x) cout << #x << "=" << x << endl
#define deb2(x, y) cout << #x << "=" << x << "," << #y << "=" << y << endl
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(x) x.begin(), x.end()
#define clr(x) memset(x, 0, sizeof(x))
#define sortall(x) sort(all(x))
#define tr(it, a) for (auto it = a.begin(); it != a.end(); it++)
#define PI 3.1415926535897932384626
typedef pair<int, int> pii;
typedef pair<ll, ll> pll;
typedef vector<int> vi;
typedef vector<ll> vl;
typedef vector<pii> vpii;
typedef vector<vi> vvi;
typedef vector<vl> vvl;
const int mod = 1000000007;
const int N = 300, M = N;
// hey there what are you looking at man? you wanna get some beers maybe? Or just a linmonade may be enough ehh? savvy?

// int main()
// {
// int x, y, n, m, temp, temp1, temp2, i, j, k, t, L, R, S, T, U, ans = 0;

// return 0;
// }

class Solution {
public:
vector<int> largestDivisibleSubset(vector<int>& nums) {
int i,j,k,temp;
int n=nums.size();
sort(nums.begin(),nums.end());
vector<int> ans(n,1);
Fo(i,n-2,-1){
Fo(j,i+1,n){
if(nums[j]%nums[i]==0){
ans[i]=max(ans[i],ans[j] + 1);
}
}
}
int ans1=0,si=0;
fo(i,n){
if(ans[i]>ans1){
ans1=ans[i];
si=i;
}

        }
        vi ret;
        ret.pb(nums[si]);
        ans1--;
        Fo(i,si+1,n){
            if(nums[i]%ret[ret.size()-1]==0 && ans[i]==ans1){
                ret.pb(nums[i]);
                ans1--;
            }
        }
        return ret;

    }

};

###################################################################################################
//Perfect Rectangle

class Solution {
public:
bool isRectangleCover(vector<vector<int>>& rectangles) {
int n = rectangles.size();

    map<pair<int, int> , int> pointCounts;

    for (auto& rect : rectangles) {
      pointCounts[{rect[0], rect[1]}]++;
      pointCounts[{rect[2], rect[3]}]++;
      pointCounts[{rect[0], rect[3]}]--;
      pointCounts[{rect[2], rect[1]}]--;
    }

    int numMarks = 0;

    for (auto it = pointCounts.begin(); it != pointCounts.end(); it++) {
      if (it->second != 0) {
        if (abs(it->second) != 1) return false;

        numMarks++;
      }
    }

    return numMarks == 4;

}

};

// Course Schedule

#include <bits/stdc++.h>
using namespace std;
#define gc getchar_unlocked
#define fo(i, n) for (i = 0; i < n; i++)
#define Fo(i, k, n) for (i = k; k < n ? i < n : i > n; k < n ? i += 1 : i -= 1)
#define debv(x) for(i=0;i<x.size();i++) cout<<x[i]<<" "
#define ll long long
#define si(x) scanf("%d", &x)
#define sl(x) scanf("%lld", &x)
#define ss(s) scanf("%s", s)
#define pi(x) printf("%d\n", x)
#define pl(x) printf("%lld\n", x)
#define ps(s) printf("%s\n", s)
#define deb(x) cout << #x << "=" << x << endl
#define deb2(x, y) cout << #x << "=" << x << "," << #y << "=" << y << endl
#define pb push_back
#define mp make_pair
#define F first
#define S second
#define all(x) x.begin(), x.end()
#define clr(x) memset(x, 0, sizeof(x))
#define sortall(x) sort(all(x))
#define tr(it, a) for (auto it = a.begin(); it != a.end(); it++)
#define PI 3.1415926535897932384626
typedef pair<int, int> pii;
typedef pair<ll, ll> pll;
typedef vector<int> vi;
typedef vector<ll> vl;
typedef vector<pii> vpii;
typedef vector<vi> vvi;
typedef vector<vl> vvl;
const int mod = 1000000007;
const int N = 300, M = N;

// code
bool ans4=true;

void DFS(int si, vector<bool> &visited , vector<bool> curr_visited, vi adj[]){
int i,j,k;
curr_visited[si]=true;
visited[si]=true;
// deb(curr_visited.size());
// debv(visited);
// debv(curr_visited);
fo(i,adj[si].size()){
if(curr_visited[adj[si][i]]==true){
// deb2(si,adj[si][i]);
ans4=false;
return;
}
if(!visited[adj[si][i]]){
DFS(adj[si][i],visited,curr_visited,adj);
}

    }

}

class Solution {
public:
bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {
ans4=true;
vi adj[numCourses];
int n=numCourses,i,j,k,temp;
fo(i,prerequisites.size()){
adj[prerequisites[i][1]].pb(prerequisites[i][0]);

        }

            // deb(adj[0][0]);

        // deb2(prerequisites.size(),prerequisites[0].size());
        vector<bool> visited(n,false), curr_visited(n,false);
        fo(i,n){
            if(!visited[i]){
                // visited[i]=true;
                DFS(i,visited,curr_visited,adj);
                if(ans4==false){
                    return false;
                }
            }
        }
        return ans4;

    }

};

###########################################################################################################################

//9. Number of Pairs satisfying Inequality

long long ans=0;

// You are given two 0-indexed integer arrays nums1 and nums2, each of size n, and an integer diff. Find the number of pairs (i, j) such that:

// 0 <= i < j <= n - 1 and
// nums1[i] - nums1[j] <= nums2[i] - nums2[j] + diff.
// nums1 -nums2 [i] <= nums1 - nums2 +diff

// nums2[i] - nums1[i] + diff >= nums2[j] - nums1 [j] ---deduction from the above statement
// nums[i] + diff >= nums[j] i<j
// nums [i] <= nums[j] + diff --final condition to look for

void pairs(vi &nums, int l, int r, int &diff){

    int i,j,k,temp;
    if(l==r){
        return;
    }
    if(abs(l-r)==1){
        nums[l] <= nums[r] + diff ? ans++ : true;
        if(nums[l]>nums[r]){

            swap(nums[l],nums[r]);

        }


        return;
    }
    int m = (l+r)/2;
    pairs(nums,l,m,diff);
    pairs(nums,m + 1,r,diff);

        // Now we have sorted two parts of the array

    Fo(i,m+1,r+1){
        int ind =upper_bound(nums.begin() + l, nums.begin() + m +1 , nums[i] + diff) - nums.begin() - 1;
        ind<=r ? ans += ind - l +1 : true;
    }
    sort(nums.begin() + l , nums.begin() + r +1);

}

class Solution {
public:
long long numberOfPairs(vector<int>& nums1, vector<int>& nums2, int diff) {
ans=0;
int i,j,k,temp;
vi nums;
fo(i,nums1.size()){
nums.pb(nums1[i]-nums2[i]);
}
// long long ans=0;
// fo(j,nums.size()){
// fo(i,j){
// nums[j]<=nums[i] + diff ? ans++ : true;
// }
// }
debv(nums);
pairs(nums, 0, nums.size()-1 , diff);
return ans;
}
};

###################################################################################################################3

//q10: . Shortest Unsorted continuous Subarray

class Solution {
public:
int findUnsortedSubarray(vector<int>& nums) {
int i,j,k,si=-1,ei=-1;
vi sorted=nums;
sort(sorted.begin(),sorted.end());
fo(i,nums.size()){
if(sorted[i]!=nums[i] && si==-1){
si=i;
ei=si;
continue;
}
if(sorted[i]!=nums[i]){
ei=i;
}

        }
        if(si==-1){
            return 0;
        }
        return ei - si +1;

    }

};

#################################################################################################################

//q11 : . Number of ways to arrive at a Destination.

// Dijkstra Algorithm
//storing (dis,node) in priority queue distance array adjacency list iin pairs priority queue helps us to give the min dis
// time complexity will be O(N + E) \* logn => O(nlogn)

int Dijkstra(vector<vector<pll>> &adj, int n, int src){
int i,j,k;
vl distances(n, LONG_MAX);
vl ways(n,0);
priority_queue<pll , vector<pll> , greater<>> nexts; // pii => {distance , node}
distances[src]=0;
ways[src]=1;
nexts.push({0,0});
while(nexts.size()>0){
auto[d, u] = nexts.top();
nexts.pop();
if(d>distances[u]){
continue;
}
for(auto [v, D] : adj[u]){
if(distances[v] > D + d){
distances[v]=D+d;
nexts.push({D+d, v});
ways[v]=ways[u];
}
// following code specifically for number of ways having min cost path
else if(distances[v] == D + d){
ways[v] = (ways[u] + ways[v]) % mod;
}
}
}
return ways[n-1];

}

class Solution {
public:
int countPaths(int n, vector<vector<int>>& roads) {
// ans=INT_MAX;
// cnt=0;
// int i,j,k,temp;
// vvi adj(n,vi(n,-1));
// fo(i,roads.size()){
// adj[roads[i][0]][roads[i][1]]= roads[i][2];
// adj[roads[i][1]][roads[i][0]]=roads[i][2];
// }
// vector<bool> visited(n,false);
// DFS(adj, 0, visited, n, 0);
// return cnt;
vector<vector<pll>> graph(n);
for(auto& road: roads) {
ll u = road[0], v = road[1], time = road[2];
graph[u].push_back({v, time});
graph[v].push_back({u, time});
}
return Dijkstra(graph, n, 0);

    }

};

##########################################################################################################################
