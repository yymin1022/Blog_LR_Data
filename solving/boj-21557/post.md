[문제 바로가기](https://boj.kr/21557)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    for(int i = 0; i < N - 3; i++){
        if(arr[0] > arr[N - 1]){
            arr[0]--;
        }else{
            arr[N - 1]--;
        }
    }

    cout << (arr[0] > arr[N - 1] ? arr[0] - 1: arr[N - 1] - 1) << "\n";

    return 0;
}

```