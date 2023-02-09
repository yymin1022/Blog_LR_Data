[문제 바로가기](https://boj.kr/11637)

```c++
#include <bits/stdc++.h>

using namespace std;

bool comp(pair<int, int> a, pair<int, int> b){
    return (a.second > b.second);
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        int sum = 0;
        vector<pair<int, int>> vote;
        for(int i = 1; i <= N; i++){
            int input;
            cin >> input;
            sum += input;
            vote.push_back(make_pair(i, input));
        }

        sort(vote.begin(), vote.end(), comp);

        if(vote[0].second == vote[1].second){
            cout << "no winner" << "\n";
        }else{
            if(vote[0].second > sum / 2){
                cout << "majority winner " << vote[0].first << "\n";
            }else{
                cout << "minority winner " << vote[0].first << "\n";
            }
        }
    }

    return 0;
}
```