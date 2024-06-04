[문제 바로가기](https://boj.kr/30970)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmpA(pair<int, int> A, pair<int, int> B){
    if(A.first == B.first){
        return A.second < B.second;
    }
    return A.first > B.first;
}

bool cmpB(pair<int, int> A, pair<int, int> B) {
    if (A.second == B.second) {
        return A.first > B.first;
    }
    return A.second < B.second;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr.push_back(make_pair(A, B));
    }

    sort(arr.begin(), arr.end(), cmpA);

    cout << arr[0].first << " ";
    cout << arr[0].second << " ";
    cout << arr[1].first << " ";
    cout << arr[1].second << "\n";

    sort(arr.begin(), arr.end(), cmpB);

    cout << arr[0].first << " ";
    cout << arr[0].second << " ";
    cout << arr[1].first << " ";
    cout << arr[1].second << "\n";

    return 0;
}
```
