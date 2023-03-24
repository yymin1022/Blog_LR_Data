[문제 바로가기](https://boj.kr/23253)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int K;
        cin >> K;

        vector<int> book;
        for(int j = 0; j < K; j++){
            int input;
            cin >> input;
            book.push_back(input);
        }

        vector<int> tmp(book);
        sort(tmp.begin(), tmp.end(), greater<int>());
        for(int j = 0; j < K; j++){
            if(book[j] != tmp[j]){
                cout << "No" << "\n";
                return 0;
            }
        }
    }

    cout << "Yes" << "\n";

    return 0;
}
```