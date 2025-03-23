[문제 바로가기](https://boj.kr/22935)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<string> arr;
    for(int i = 1; i < 16; i++){
        string tmp;
        for(int j = 3; j >= 0; j--){
            tmp.append((i & 1 << j) != 0 ? "딸기" : "V");
        }
        arr.push_back(tmp);
    }

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        N--;
        N %= 28;

        if(N < 15){
            cout << arr[N] << "\n";
        }else{
            cout << arr[28 - N] << "\n";
        }
    }

    return 0;
}
```