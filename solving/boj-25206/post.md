[문제 바로가기](https://boj.kr/25206)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    double cnt = 0;
    double sum = 0;
    for(int i = 0; i < 20; i++){
        string subject;
        double score;
        string result;
        cin >> subject >> score >> result;

        if(result != "P"){
            if(result == "A+"){
                sum += 4.5 * score;
            }else if(result == "A0"){
                sum += 4.0 * score;
            }else if(result == "B+"){
                sum += 3.5 * score;
            }else if(result == "B0"){
                sum += 3.0 * score;
            }else if(result == "C+"){
                sum += 2.5 * score;
            }else if(result == "C0"){
                sum += 2.0 * score;
            }else if(result == "D+"){
                sum += 1.5 * score;
            }else if(result == "D0"){
                sum += 1.0 * score;
            }
            cnt += score;
        }
    }

    if(cnt == 0){
        cout << "0.000000" << "\n";
    }

    cout << fixed;
    cout.precision(6);
    cout << sum / cnt << "\n";

    return 0;
}
```