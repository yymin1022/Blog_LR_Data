[문제 바로가기](https://boj.kr/1717)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1000001];

int findSet(int N){
    if(N == arr[N]){
        return N;
    }

    arr[N] = findSet(arr[N]);
    return arr[N];
}

void unionSet(int N, int M){
    N = findSet(N);
    M = findSet(M);

    if(N != M){
        arr[N] = M;
    }
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        arr[i] = i;
    }

    for(int i = 0; i < M; i++){
        int cmd, A, B;
        cin >> cmd >> A >> B;

        if(cmd == 0){
            unionSet(A, B);
        }else{
            if(findSet(A) == findSet(B)){
                cout << "YES" << "\n";
            }else{
                cout << "NO" << "\n";
            }
        }
    }

    return 0;
}

```