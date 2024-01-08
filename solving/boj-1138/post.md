[문제 바로가기](https://boj.kr/1138)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> people;
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        people.push_back(input);
    }

    vector<int> ans(N);
    for(int i = 0; i < N; i++){
        int cnt = 0;
        for(int j = 0; j < N; j++){
            if(people[i] == cnt && ans[j] == 0){
                ans[j] = i + 1;
                break;
            }else if(ans[j] == 0){
                cnt++;
            }
        }
    }

    for(int i = 0; i < N; i++){
        cout << ans[i] << " ";
    }

    return 0;
}

```
