[문제 바로가기](https://boj.kr/11116)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N--){
        int M;
        cin >> M;

        vector<int> left;
        for(int i = 0; i < M; i++){
            int input;
            cin >> input;
            left.push_back(input);
        }

        vector<int> right;
        for(int i = 0; i < M; i++){
            int input;
            cin >> input;
            right.push_back(input);
        }

        int ans = 0;
        for(int i = 0; i < M; i++){
            for(int j = i + 1; j < M; j++){
                if(left[j] == left[i] + 500){
                    for(int k = 0; k < M; k++){
                        if(right[k] == left[i] + 1000){
                            ans++;
                            j = M;
                            break;
                        }
                    }
                }
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```