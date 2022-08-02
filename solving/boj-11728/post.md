[문제 바로가기](https://boj.kr/11728)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> A;
    vector<int> B;
    for(int i = 0; i < N; i++){
        int temp;
        cin >> temp;
        A.push_back(temp);
    }
    for(int i = 0; i < M; i++){
        int temp;
        cin >> temp;
        B.push_back(temp);
    }

    sort(A.begin(), A.end());
    sort(B.begin(), B.end());

    int fromA = 0;
    int fromB = 0;
    vector<int> result;
    while(fromA < N && fromB < M){
        if(A[fromA] < B[fromB]){
            result.push_back(A[fromA]);
            fromA++;
        }else if(A[fromA] > B[fromB]){
            result.push_back(B[fromB]);
            fromB++;
        }else{
            result.push_back(A[fromA]);
            result.push_back(B[fromB]);
            fromA++;
            fromB++;
        }
    }

    while(fromA < N){
        result.push_back(A[fromA]);
        fromA++;
    }
    while(fromB < M){
        result.push_back(B[fromB]);
        fromB++;
    }

    for(int i = 0; i < result.size(); i++){
        cout << result[i] << " ";
    }

    return 0;
}```