[문제 바로가기](https://boj.kr/29615)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> student;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        student.push_back(input);
    }

    vector<int> friends;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        friends.push_back(input);
    }

    int ans = 0;
    for(int i = 0; i < M; i++){
        bool isFriend = false;
        for(int j = 0; j < M; j++){
            if(student[i] == friends[j]){
                isFriend = true;
                break;
            }
        }
        if(!isFriend){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
