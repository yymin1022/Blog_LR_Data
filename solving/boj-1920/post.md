[문제 바로가기](https://boj.kr/1920)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> A;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        A.push_back(input);
    }

    sort(A.begin(), A.end());

    int M;
    cin >> M;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        cout << binary_search(A.begin(), A.end(), input) << "\n";
    }
    
    return 0;
}```