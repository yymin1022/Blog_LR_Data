[문제 바로가기](https://boj.kr/1461)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> book;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        book.push_back(input);
    }

    book.push_back(0);
    sort(book.begin(), book.end());

    int zero;
    for(int i = 0; i <= N; i++){
        if(book[i] == 0){
            zero = i;
            break;
        }
    }

    int ans = 0;
    for(int i = 0; i < zero; i += M){
        ans += abs(book[i] * 2);
    }

    for(int i = N; i > zero; i -= M){
        ans += book[i] * 2;
    }

    ans -= max(abs(book[0]), book[N]);

    cout << ans << "\n";

    return 0;
}
```