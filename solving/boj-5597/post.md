[문제 바로가기](https://boj.kr/5597)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<int> student(31, 0);
    for(int i = 0; i < 28; i++){
        int input;
        cin >> input;
        student[input] = 1;
    }

    for(int i = 1; i < 31; i++){
        if(!student[i]){
            cout << i << "\n";
        }
    }

    return 0;
}```