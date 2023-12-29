[문제 바로가기](https://boj.kr/11508)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> price;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        price.push_back(input);
    }

    sort(price.begin(), price.end(), greater<>());

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(i % 3 != 2){
            ans += price[i];
        }
    }

    cout << ans << "\n";

    return 0;
}
```