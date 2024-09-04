[문제 바로가기](https://boj.kr/7774)

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

    sort(A.begin(), A.end(), greater<int>());
    sort(B.begin(), B.end(), greater<int>());

    int ansA = 0;
    int ansB = 0;
    for(int i = 0; i < A.size(); i++){
        ansB += A[i];

        if(i != 0 && ansA != 0){
            ansA--;
        }

        while(true){
            if(B.empty()){
                cout << ansA << "\n";
                return 0;
            }

            if(ansB == 0){
                break;
            }else{
                ansB--;
                if(!B.empty()){
                    ansA += B[0];
                    B.erase(B.begin());
                }
            }
        }
    }

    cout << ansA << "\n";

    return 0;
}
```