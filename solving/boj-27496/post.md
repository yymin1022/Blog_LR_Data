[문제 바로가기](https://boj.kr/27496)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int C = 0;
    for(int i = 0; i < L; i++){
        C += arr[i];
        if(129 <= C && C <= 138){
            ans++;
        }
    }

    for(int i = L; i < N; i++){
        C += arr[i] - arr[i - L];
        if(129 <= C && C <= 138){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```
