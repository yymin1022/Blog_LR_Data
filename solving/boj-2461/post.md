[문제 바로가기](https://boj.kr/2461)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<int, int>> student;
    for(int i = 0; i < N; i++){
        for(int j = 0;j < M; j++){
            int input;
            cin >> input;
            student.push_back(make_pair(input, i));
        }
    }

    sort(student.begin(), student.end());

    int ans = 2147483647;
    int num = 0;
    int left = 0;
    int right = 0;
    while(right < N * M){
        if(cnt[student[right].second] == 0){
            num++;
        }
        cnt[student[right].second]++;
        right++;

        while(num == N){
            ans = min(student[right - 1].first - student[left].first, ans);
            cnt[student[left].second]--;

            if(cnt[student[left].second] == 0){
                num--;
            }
            left++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```