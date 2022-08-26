[문제 바로가기](https://boj.kr/1202)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<pair<int, int>> jewel;
    for (int i = 0; i < N; i++){
        int M, V;
        cin >> M >> V;
        jewel.push_back(make_pair(M, V));
    }

    vector<int> bag;
    for (int i = 0; i < K; i++){
        int input;
        cin >> input;
        bag.push_back(input);
    }

    sort(jewel.begin(), jewel.end());
    sort(bag.begin(), bag.end());

    int idx = 0;
    long long ans = 0;
    priority_queue<int> pq;
    for(int x = 0 ; x < K ; x++){
        while(idx < N && jewel[idx].first <= bag[x]){
            pq.push(jewel[idx].second);
            idx++;
        }

        if(!pq.empty()){
            ans += pq.top();
            pq.pop();
        }
    }

    cout << ans << "\n";

    return 0;
}
}```