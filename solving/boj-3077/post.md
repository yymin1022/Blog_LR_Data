[문제 바로가기](https://boj.kr/3077)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, int> ans;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        ans[input] = i;
    }

    vector<string> student;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        student.push_back(input);
    }

    int cnt = 0;
    for(int i = 0; i < N - 1; i++){
        for(int j = i + 1; j < N; j++){
            if(ans[student[i]] < ans[student[j]]){
                cnt++;
            }
        }
    }

    cout << cnt << "/" << N * (N - 1) / 2 << "\n";

    return 0;
}
```