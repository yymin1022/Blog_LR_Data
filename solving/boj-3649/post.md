[문제 바로가기](https://boj.kr/3649)

```c++
#include <bits/stdc++.h>

using namespace std;

int check(string, bool);

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, X;
    while(cin >> X >> N){
        vector<int> lego;
        for(int i = 0; i < N; i++){
            int l;
            cin >> l;
            lego.push_back(l);
        }

        sort(lego.begin(), lego.end());
        X *= 10000000;

        bool isAble = false;
        int fromL = 0;
        int fromR = N - 1;
        while(fromL < fromR){
            int sum = lego[fromL] + lego[fromR];

            if(sum == X){
                cout << "yes " << lego[fromL] << " " << lego[fromR] << "\n";
                isAble = true;
                break;
            }else{
                if(sum < X){
                    fromL++;
                }else{
                    fromR--;
                }
            }
        }

        if(!isAble){
            cout << "danger\n";
        }
    }

    return 0;
}
```