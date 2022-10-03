[문제 바로가기](https://boj.kr/25703)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cout << "int a;" << "\n";
    for(int i = 1; i <= N; i++){
        cout << "int" << " ";

        for(int j = 0; j < i; j++){
            cout << "*";
        }

        cout << "ptr";

        if(i > 1){
            cout << i;
        }

        cout << " = &";
        if(i == 1){
            cout << "a;" << "\n";
        }else{
            cout << "ptr";

            if(i > 2){
                cout << i - 1;
            }

            cout << ";" << "\n";
        }
    }

    return 0;
}
```