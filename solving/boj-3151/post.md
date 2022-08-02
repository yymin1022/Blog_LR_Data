[문제 바로가기](https://boj.kr/3151)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
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

    long long answer = 0;
    for(int i = 0; i < N - 2; i++){
        for(int j = i + 1; j < N - 1; j++){
            int sum = (student[i] + student[j]) * -1;
            int start = lower_bound(student.begin() + j + 1, student.end(), sum) - student.begin();
            int end = upper_bound(student.begin() + j + 1, student.end(), sum) - student.begin();

            answer += end - start;
        }
    }

    cout << answer << "\n";

    return 0;
}
```