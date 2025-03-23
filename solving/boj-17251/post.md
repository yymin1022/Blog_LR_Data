[문제 바로가기](https://boj.kr/17251)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1000001];
int blue[1000001];
int red[1000001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        cin >> arr[i];
    }

    for(int i = 1; i <= N; i++){
        red[i] = max(arr[i], red[i - 1]);
    }

    for(int i = N; i > 0; i--){
        blue[i] = max(arr[i], blue[i + 1]);
    }

    int cntBlue = 0;
    int cntRed = 0;
    for(int i = 1; i < N; i++){
        if(red[i] > blue[i + 1]){
            cntRed++;
        }else if(red[i] < blue[i + 1]){
            cntBlue++;
        }
    }

    if(cntBlue > cntRed){
        cout << "B" << "\n";
    }else if(cntBlue < cntRed){
        cout << "R" << "\n";
    }else{
        cout << "X" << "\n";
    }

    return 0;
}
```