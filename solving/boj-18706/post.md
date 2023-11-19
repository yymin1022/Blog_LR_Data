[문제 바로가기](https://boj.kr/18706)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    int s, m, l;
} price;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int C, P;
        cin >[..](..)> C >> P;

        map<string, price> coffee;
        for(int i = 0; i < C; i++){
            string name;
            int s, m, l;
            cin >> name >> s >> m >> l;
            coffee[name] = {s, m, l};
        }

        for(int i = 0; i < P; i++){
            string name, size, menu;
            cin >> name >> size >> menu;

            int price = 100 / P + (size == "small" ? coffee[menu].s : size == "medium" ? coffee[menu].m : coffee[menu].l);
            if(price % 10 == 4 || price % 10 == 9){
                price++;
            }else if(price % 10 == 6 || price % 10 == 1){
                price--;
            }
            cout << name << " ";
            cout << price << "\n";
        }
    }

    return 0;
}
```