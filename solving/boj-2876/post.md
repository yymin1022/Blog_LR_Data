[문제 바로가기](https://boj.kr/2876)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> A;
    vector<int> B;
    for(int i = 0; i < N; i++){
        int inputA, inputB;
        cin >> inputA >> inputB;
        A.push_back(inputA);
        B.push_back(inputB);
    }

    int ansLen = 0;
    int ansVal = 0;
    for(int i = 1; i <= 5; i++){
        int tmp = 0;
        for(int j = 0; j < N; j++){
            if(i == A[j] || i == B[j]){
                tmp++;
            }else{
                tmp = 0;
            }

            if(tmp > ansLen){
                ansLen = tmp;
                ansVal = i;
            }
        }
    }

    cout << ansLen << " ";
    cout << ansVal << "\n";

    return 0;
}

```