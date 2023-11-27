[문제 바로가기](https://boj.kr/10431)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int P;
    cin >> P;

    while(P--){
        int T;
        cin >> T;

        vector<int> students;
        for(int i = 0; i < 20; i++){
            int input;
            cin >> input;
            students.push_back(input);
        }

        int ans = 0;
        for(int i = 0; i < 20; i++){
            for(int j = i; j < 20; j++){
                if(students[i] > students[j]){
                    ans++;
                }
            }
        }

        cout << T << " ";
        cout << ans << "\n";
    }

    return 0;
}
```