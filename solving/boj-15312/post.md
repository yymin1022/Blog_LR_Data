[문제 바로가기](https://boj.kr/15312)

```c++
#include <bits/stdc++.h>

using namespace std;

int num[26] = {3, 2, 1, 2, 3, 3, 2, 3, 3, 2, 2, 1, 2, 2, 1, 2, 2, 2, 1, 2, 1, 1, 1, 2, 2, 1};

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string A, B;
    cin >> A >> B;

    vector<int> data;
    for(int i = 0; i < A.size(); i++){
        data.push_back(num[A[i] - 'A']);
        data.push_back(num[B[i] - 'A']);
    }

    while(true){
        vector<int> tmp;
        for(int i = 0; i < data.size() - 1; i++){
            tmp.push_back((data[i] + data[i + 1]) % 10);
        }

        data = tmp;
        if(data.size() == 2){
            cout << data[0] << data[1] << "\n";
            break;
        }
    }

    return 0;
}

```