[문제 바로가기](https://boj.kr/14670)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<int, int> medicine;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        medicine[A] = B + 1;
    }

    int R;
    cin >> R;
    for(int i = 0; i < R; i++){
        int L;
        cin >> L;

        vector<int> ans;
        for(int j = 0; j < L; j++){
            int S;
            cin >> S;

            if(medicine[S] != 0){
                ans.push_back(medicine[S] - 1);
            }
        }

        if(ans.size() == L){
            for(int j = 0; j < ans.size(); j++){
                cout << ans[j] << " ";
            }
            cout << "\n";
        }else{
            cout << "YOU DIED" << "\n";
        }
    };

    return 0;
}
```