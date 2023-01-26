[문제 바로가기](https://boj.kr/13333)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> docs;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        docs.push_back(input);
    }

    sort(docs.begin(), docs.end());

    for(int i = 0; i <= N; i++){
        int tmp = docs.end() - lower_bound(docs.begin(), docs.end(), i);
        if(tmp >= i && docs[N - i - 1] <= i){
            cout << i << "\n";
        }
    }

    return 0;
}
```