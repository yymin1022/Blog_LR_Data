[문제 바로가기](https://boj.kr/23028)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, A, B;
    cin >> N >> A >> B;

    vector<pair<int, int>> subject;
    for(int i = 0; i < 10; i++){
        int X, Y;
        cin >> X >> Y;
        subject.push_back(make_pair(X, Y));
    }

    int idx = 0;
    N = 8 - N;
    while(N--){
        int tmp = 6;
        A += min(subject[idx].first, tmp) * 3;
        B += min(subject[idx].first, tmp) * 3;
        tmp -= min(subject[idx].first, tmp);

        B += min(subject[idx].second, tmp) * 3;
        idx++;
    }

    if(A >= 66 && B >= 130){
        cout << "Nice" << "\n";
    }else{
        cout << "Nae ga wae" << "\n";
    }

    return 0;
}

```