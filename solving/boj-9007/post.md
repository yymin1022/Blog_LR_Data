[문제 바로가기](https://boj.kr/9007)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int K, N;
        cin >> K >> N;

        vector<int> team[4];
        vector<int> teamSum[2];
        for(int i = 0; i < 4; i++){
            for(int j = 0; j < N; j++){
                int input;
                cin >> input;
                team[i].push_back(input);
            }
        }

        for(int i = 0; i < N; i++){
            for(int j = 0; j < N; j++){
                teamSum[0].push_back(team[0][i] + team[1][j]);
                teamSum[1].push_back(team[2][i] + team[3][j]);
            }
        }

        sort(teamSum[1].begin(), teamSum[1].end());

        bool isFound = false;
        int ans = 987654321;
        for(int i = 0; i < N * N; i++){
            int fromL = 0;
            int fromR = N * N - 1;
            int sum;

            while(fromL <= fromR){
                int mid = (fromL + fromR) / 2;
                sum = teamSum[0][i] + teamSum[1][mid];

                if(abs(K - ans) > abs(K - sum)){
                    ans = sum;
                }else if(abs(K - ans) == abs(K - sum)){
                    ans = min(sum, ans);
                }

                if(sum < K){
                    fromL = mid + 1;
                }else if(sum > K){
                    fromR = mid - 1;
                }else{
                    isFound = true;
                    break;
                }
            }

            if(isFound){
                break;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```