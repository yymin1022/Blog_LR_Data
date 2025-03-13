[문제 바로가기](https://boj.kr/10984)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    cout << fixed;
    cout.precision(1);

    while(T--){
        int N;
        cin >> N;

        double grade = 0;
        int total = 0;
        for(int i = 0; i < N; i++){
            int C;
            double G;
            cin >> C >> G;

            grade += C * G;
            total += C;
        }

        cout << total << " ";
        cout << grade / total << "\n";
    }

    return 0;
}
```