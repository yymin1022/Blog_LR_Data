[문제 바로가기](https://boj.kr/13414)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<string, int> A, pair<string, int> B){
    return A.second < B.second;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int K, L;
    cin >> K >> L;

    map<string, int> student;
    for(int i = 0; i < L; i++){
        string input;
        cin >> input;

        student[input] = i;
    }

    vector<pair<string, int>> tmp(student.begin(), student.end());
    sort(tmp.begin(), tmp.end(), cmp);

    for(int i = 0; i < min(K, (int)tmp.size()); i++){
        cout << tmp[i].first << "\n";
    }

    return 0;
}
```