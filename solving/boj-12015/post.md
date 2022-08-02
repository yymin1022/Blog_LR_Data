[문제 바로가기](https://boj.kr/12015)

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

        if(A.empty() || A.back() < input){
            A.push_back(input);
        }else{
            int idx = lower_bound(A.begin(), A.end(), input) - A.begin();
            A[idx] = input;
        }
    }

    cout << A.size() << "\n";

    return 0;
}```