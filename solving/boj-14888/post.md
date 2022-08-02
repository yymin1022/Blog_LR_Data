[문제 바로가기](https://boj.kr/14888)

```c++
#include <bits/stdc++.h>

using namespace std;

void solve(int, int);

int N;
int minN = 987654321;
int maxN = -987654321;
vector<int> nums(11);
vector<int> oper(4);

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;
    for(int i = 0; i < N; i++){
        cin >> nums[i];
    }
    for(int i = 0; i < 4; i++){
        cin >> oper[i];
    }

    solve(nums[0],1);

    cout << maxN << "\n" << minN << "\n";
}

void solve(int result, int idx){
    if(idx == N){
        maxN = max(maxN, result);
        minN = min(minN, result);
        return;
    }

    for(int i = 0; i < 4; i++){
        if(oper[i] > 0){
            oper[i]--;

            if(i == 0){
                solve(result + nums[idx], idx + 1);
            }else if(i == 1){
                solve(result - nums[idx], idx + 1);
            }else if(i == 2){
                solve(result * nums[idx], idx + 1);
            }else{
                solve(result / nums[idx], idx + 1);
            }

            oper[i]++;
        }
    }
}```