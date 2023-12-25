[문제 바로가기](https://boj.kr/2238)

```c++
#include  <bits/stdc++.h>

using namespace std;

int price[1000001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int U, N;
    cin >> U >> N;

    vector<pair<string, int>> tmp(N);
    for (int i = 0; i < N; i++) {
        cin >> tmp[i].first >> tmp[i].second;
        price[tmp[i].second]++;
    }

    int minPrice = 1000001;
    for(int i = 1; i < 1000001; i++){
        if(price[i] > 0) {
            minPrice = min(price[i], minPrice);
        }
    }

    vector<int> ans;
    for(int i = 1; i < 1000001; i++){
        if(price[i] == minPrice) {
            ans.push_back(i);
        }
    }

    sort(ans.begin(), ans.end());

    for(int i = 0; i < N; i++){
        if(tmp[i].second == ans[0]){
            cout << tmp[i].first << " ";
            cout << tmp[i].second << "\n";
            break;
        }
    }

    return 0;
}
```