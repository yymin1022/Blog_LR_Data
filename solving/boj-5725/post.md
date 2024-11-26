[문제 바로가기](https://boj.kr/5725)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int N;
        cin >> N;
        if(N == 0){
            break;
        }

        vector<int> C, P;
        for(int i = 0; i < N; i++){
            int c, p;
            cin >> c >> p;

            C.push_back(c);
            P.push_back(p);
        }

        bool flag = true;
        vector<int> grid(N, -1);
        for(int i = 0; i < N; i++){
            int position = i + P[i];
            if(position < 0 || position >= N || grid[position] != -1){
                flag = false;
                break;
            }
            grid[position] = C[i];
        }

        if(flag){
            for(int i = 0; i < N; i++){
                cout << grid[i] << " ";
            }
        }else{
            cout << "-1";
        }

        cout << "\n";
    }

    return 0;
}

```
