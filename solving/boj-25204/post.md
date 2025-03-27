[문제 바로가기](https://boj.kr/25204)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(string A, string B){
    int idxA = 0;
    int idxB = 0;
    while(idxA < A.size() && idxB < B.size()){
        if(A[idxA] == B[idxB]){
            idxA++;
            idxB++;
        }else{
            if(A[idxA] == '-'){
                return false;
            }
            if(B[idxB] == '-'){
                return true;
            }

            char tmpA = tolower(A[idxA]);
            char tmpB = tolower(B[idxB]);
            if(tmpA != tmpB){
                return tmpA < tmpB;
            }

            return A[idxA] < B[idxB];
        }
    }

    return A < B;
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<string> arr;
        for(int i = 0;i < N; i++){
            string input;
            cin >> input;
            arr.push_back(input);
        }

        sort(arr.begin(), arr.end(), cmp);

        for(int i = 0; i < N; i++){
            cout << arr[i] << "\n";
        }
    }

    return 0;
}
```