[문제 바로가기](https://boj.kr/14468)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    string S;
    cin >> S;

    int ans = 0;
    vector<bool> isCame(26, false);
    stack<char> cow;
    for(int i = 0; i < 52; i++){
        if(cow.empty() || !isCame[S[i] - 'A']){
            cow.push(S[i]);
            isCame[S[i] - 'A'] = true;
        }else if(cow.top() == S[i]){
            cow.pop();
        }else{
            int cnt = 0;
            stack<char> temp;
            while(cow.top() != S[i]){
                temp.push(cow.top());
                cow.pop();

                cnt++;
            }

            cow.pop();

            while(!temp.empty()){
                cow.push(temp.top());
                temp.pop();
            }

            ans += cnt;
        }
    }

    cout << ans << "\n";
    
    return 0;
}```