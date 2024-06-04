[문제 바로가기](https://boj.kr/1822)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> A;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        A.push_back(input);
    }

    vector<int> B;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        B.push_back(input);
    }

    sort(B.begin(), B.end());

    vector<int> ans;
    for(int i = 0; i < N; i++){
        if(binary_search(B.begin(), B.end(), A[i]) == 0){
            ans.push_back(A[i]);
        }
    }

    sort(ans.begin(), ans.end());

    cout << ans.size() << "\n";
    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}
```
