[문제 바로가기](https://boj.kr/14612)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<int, int>> order;
    while(N--){
        string cmd;
        cin >> cmd;

        if(cmd == "order"){
            int n, t;
            cin >> n >> t;
            order.push_back(make_pair(t, n));
        }else if(cmd == "complete"){
            int n;
            cin >> n;

            for(int i = 0; i < order.size(); i++){
                if(order[i].second == n){
                    order.erase(order.begin() + i);
                }
            }
        }else{
            sort(order.begin(), order.end());
        }

        if(order.empty()){
            cout << "sleep";
        }else{
            for(int i = 0; i < order.size(); i++){
                cout << order[i].second << " ";
            }
        }
        cout << "\n";
    }

    return 0;
}
```