[문제 바로가기](https://boj.kr/20546)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> price;
    for(int i = 0; i < 14; i++){
        int input;
        cin >> input;
        price.push_back(input);
    }

    int moneyBNP = N;
    int moneyTM = N;
    int stockBNP = 0;
    int stockTM = 0;
    for(int i = 0; i < 14; i++){
        if(price[i] <= moneyBNP){
            int tmp = moneyBNP / price[i];
            stockBNP += tmp;
            moneyBNP -= tmp * price[i];
        }

        if(i > 2 && stockTM > 0 && price[i - 3] < price[i - 2] && price[i - 2] < price[i - 1] && price[i - 1] < price[i]){
            moneyTM += price[i] * stockTM;
            stockTM = 0;
        }else if(i > 2 && moneyTM > 0 && price[i - 3] > price[i - 2] && price[i - 2] > price[i - 1] && price[i - 1] > price[i]){
            if(price[i] <= moneyTM){
                int tmp = moneyTM / price[i];
                stockTM += tmp;
                moneyTM -= tmp * price[i];
            }
        }
    }

    int BNP = stockBNP * price[13] + moneyBNP;
    int TIMING = stockTM * price[13] + moneyTM;

    cout << (BNP == TIMING ? "SAMESAME" : (BNP > TIMING ? "BNP" : "TIMING")) << "\n";

    return 0;
}
```