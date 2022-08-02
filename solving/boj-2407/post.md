[문제 바로가기](https://boj.kr/2407)

```c++
#include <bits/stdc++.h>

using namespace std;

string comb(int, int);
string bigNumAdd(string, string);
string dp[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N;
    cin >> N >> M;

    cout << comb(N, M) << "\n";

    return 0;
}

string bigNumAdd(string a, string b){
    int sum = 0;
    string result = "";

    while(!a.empty() || !b.empty() || sum > 0){
        if(!a.empty()){
            sum += a.back() - '0';
            a.pop_back();
        }
        if(!b.empty()){
            sum += b.back() - '0';
            b.pop_back();
        }

        result.push_back((sum % 10) + '0');
        sum /= 10;
    }

    reverse(result.begin(), result.end());
    return result;
}

string comb(int tempN, int tempM){
    if(tempN == tempM || tempM == 0){
        return "1";
    }
    if(dp[tempN][tempM] == ""){
        dp[tempN][tempM] = bigNumAdd(comb(tempN - 1, tempM - 1), comb(tempN - 1, tempM));
    }
    
    return dp[tempN][tempM];
}```