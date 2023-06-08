[문제 바로가기](https://boj.kr/4383)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    while(true){
        int N;
        cin >> N;

        if(cin.eof() == 1){
            break;
        }

        if(N == 1){
            cin >> N;
            cout << "Jolly" << "\n";
            continue;
        }

        int num;
        cin >> num;

        vector<bool> arr(N, false);
        for(int i = 1; i < N; i++){
            int tmp;
            cin >> tmp;

            int sub = abs(num - tmp);
            if(sub > 0 && sub < N){
                arr[abs(num - tmp)] = true;
            }

            num = tmp;
        }

        bool isJolly = true;
        for(int i = 1; i < N; i++){
            if(!arr[i]){
                isJolly = false;
                break;
            }
        }

        if(isJolly){
            cout << "Jolly" << "\n";
        }else{
            cout << "Not jolly" << "\n";
        }
    }

    return 0;
}
```