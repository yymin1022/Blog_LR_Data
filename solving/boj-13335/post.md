[문제 바로가기](https://boj.kr/13335)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, W, L;
    cin >> N >> W >> L;

    queue<int> truck;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        truck.push(input);
    }

    int ans = 0;
    int weight = 0;
    deque<pair<int, int>> bridge;
    while(true){
        ans++;
        if(truck.empty() && bridge.empty()){
            break;
        }

        int cur = truck.front();

        if(!truck.empty() && weight + cur <= L){
            bridge.push_back(make_pair(cur, 0));
            weight += cur;
            truck.pop();
        }

        for(int i = 0; i < bridge.size(); i++){
            bridge[i].second++;
        }

        if(bridge.front().second == W){
            weight -= bridge.front().first;
            bridge.pop_front();
        }
    }

    cout << ans << "\n";

    return 0;
}

```