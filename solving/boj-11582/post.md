[문제 바로가기](https://boj.kr/11582)

```c++
#include  <bits/stdc++.h>

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
    
    int K;
    cin >> K;

    int num = N / 2;
    while(num >= 1){
        int size = N / num;

        for(int i = 0; i < N - 1; i += size){
            sort(arr.begin() + i, arr.begin() + i + size);
        }

        if(num == K){
            for(int i = 0; i < N; i++){
                cout << arr[i] << ' ';
            }

            cout << "\n";
            break;
        }

        num /= 2;
    }

    return 0;
}
```