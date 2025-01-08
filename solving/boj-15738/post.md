[문제 바로가기](https://boj.kr/15738)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K, M;
    cin >> N >> K >> M;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(i + 1);
    }

    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        if(input > 0){
            reverse(arr.begin(), arr.begin() + input);
        }else{
            input *= -1;
            reverse(arr.end() - input, arr.end());
        }
    }

    for(int i = 0; i < N; i++){
        if(arr[i] == K){
            cout << i + 1 << "\n";
            break;
        }
    }

    return 0;
}

```