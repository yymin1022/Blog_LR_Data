[문제 바로가기](https://boj.kr/23301)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, T;
    cin >> N >> T;

    int maxTime = 0;
    map<int, int> time;
    for(int i = 0; i < N; i++){
        int K;
        cin >> K;

        for(int j = 0; j < K; j++){
            int from, to;
            cin >> from >> to;

            maxTime = max(to, maxTime);
            for(int k = from; k < to; k++){
                time[k]++;
            }
        }
    }

    int ansFrom = 0;
    int ansTo = 0;
    int ansVal = 0;
    for(int i = 0; i <= maxTime - T; i++){
        int tmp = 0;
        for(int j = i; j < i + T; j++){
            tmp += time[j];
        }

        if(tmp > ansVal){
            ansFrom = i;
            ansTo = i + T;
            ansVal = tmp;
        }
    }

    cout << ansFrom << " ";
    cout << ansTo << "\n";

    return 0;
}

```