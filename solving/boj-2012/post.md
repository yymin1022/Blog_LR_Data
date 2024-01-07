[문제 바로가기](https://boj.kr/2012)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> student;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        student.push_back(input);
    }

    sort(student.begin(), student.end());

    long long ans = 0;
    for(int i = 0; i < N; i++){
        ans += abs(student[i] - i - 1);
    }

    cout << ans << "\n";

    return 0;
}
```