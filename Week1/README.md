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
