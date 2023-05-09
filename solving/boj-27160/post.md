[문제 바로가기](https://boj.kr/27160)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, int> fruit;
    for(int i = 0; i < N; i++){
        string S;
        int cnt;
        cin >> S >> cnt;
        fruit[S] += cnt;
    }

    for(auto iter: fruit){
        if(iter.second == 5){
            cout << "YES" << "\n";
            return 0;
        }
    }

    cout << "NO" << "\n";

    return 0;
}
```