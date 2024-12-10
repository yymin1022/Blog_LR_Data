[문제 바로가기](https://boj.kr/1244)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<bool> arr(N + 1);
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        arr[i] = input;
    }

    int M;
    cin >> M;

    while(M--){
        int A, B;
        cin >> A >> B;

        if(A == 1){
            for(int i = B; i <= N; i += B){
                arr[i] = !arr[i];
            }
        }else{
            arr[B] = !arr[B];
            for(int i = 1; B + i <= N && B - i > 0; i++){
                if(arr[B + i] != arr[B - i]){
                    break;
                }
                arr[B + i] = !arr[B + i];
                arr[B - i] = !arr[B - i];
            }
        }
    }

    for(int i = 1; i <= N; i++){
        cout << arr[i] << " ";

        if(i % 20 == 0){
            cout << "\n";
        }
    }

    return 0;
}
```