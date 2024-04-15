[문제 바로가기](https://boj.kr/23895)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int N, B;
        cin >> N >> B;

        vector<int> A;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            A.push_back(input);
        }

        sort(A.begin(), A.end());

        int ans = 0;
        for(int i = 0; i < N; i++){
            if(A[i] <= B){
                ans++;
                B -= A[i];
            }else{
                break;
            }
        }

        cout << "Case #" << t << ": ";
        cout << ans << "\n";
    }

    return 0;
}
```