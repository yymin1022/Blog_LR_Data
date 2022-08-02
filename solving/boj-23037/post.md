[문제 바로가기](https://boj.kr/23037)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int num;
    cin >> num;

    int answer = 0;
    for(int i = 0; i < 5; i++){
        int temp = num % 10;
        answer += pow(temp, 5);
        num /= 10;
    }

    cout << answer << "\n";

    return 0;
}```