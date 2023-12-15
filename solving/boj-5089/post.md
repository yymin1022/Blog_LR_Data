[문제 바로가기](https://boj.kr/5089)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int week = 1;
    while(N){
        set<string> city;
        cin.ignore();
        for(int i = 0; i < N; i++){
            string input;
            getline(cin, input);
            city.insert(input);
        }

        cout << "Week " << week << " ";
        cout << city.size() << "\n";
        week++;

        cin >> N;
    }

    return 0;
}
```