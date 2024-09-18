[문제 바로가기](https://boj.kr/25329)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<long long, string> A, pair<long long, string> B){
    if(A.first == B.first){
        return A.second < B.second;
    }
    return A.first > B.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, long long> data;
    for(int i = 0; i < N; i++){
        string time, name;
        cin >> time >> name;

        long long hour = (time[0] - '0') * 10 + time[1] - '0';
        long long min = (time[3] - '0') * 10 + time[4] - '0';
        data[name] += hour * 60 + min;
    }

    vector<pair<long long, string>> arr;
    for(auto iter = data.begin(); iter != data.end(); iter++){
        long long cost = 10;
        if(iter->second > 100){
            cost += (iter->second - 100) / 50 * 3 + ((iter->second - 100) % 50 != 0 ? 3 : 0);
        }
        arr.push_back(make_pair(cost, iter->first));
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < arr.size(); i++){
        cout << arr[i].second << " ";
        cout << arr[i].first << "\n";
    }

    return 0;
}
```