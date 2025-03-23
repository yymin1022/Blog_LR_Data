[문제 바로가기](https://boj.kr/1063)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    char Kc, Rc, Kr, Rr;
    int N;
    cin >> Kc >> Kr >> Rc >> Rr >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        if(input == "L"){
            if(Kc - 1 == Rc && Kr == Rr){
                if(Rc - 1 >= 'A'){
                    Kc--;
                    Rc--;
                }
            }else if(Kc - 1 >= 'A'){
                Kc--;
            }
        }else if(input == "LT"){
            if(Kc - 1 == Rc && Kr + 1 == Rr){
                if(Rc - 1 >= 'A' && Rr + 1 <= '8'){
                    Kc--;
                    Kr++;
                    Rc--;
                    Rr++;
                }
            }else if(Kc - 1 >= 'A' && Kr + 1 <= '8'){
                Kc--;
                Kr++;
            }
        }else if(input == "T"){
            if(Kc == Rc && Kr + 1 == Rr){
                if(Rr + 1 <= '8'){
                    Kr++;
                    Rr++;
                }
            }else if(Kr + 1 <= '8'){
                Kr++;
            }
        }else if(input == "RT"){
            if(Kc + 1 == Rc && Kr + 1 == Rr){
                if(Rc + 1 <= 'H' && Rr + 1 <= '8'){
                    Kc++;
                    Rc++;
                    Kr++;
                    Rr++;
                }
            }else if(Kc + 1 <= 'H' && Kr + 1 <= '8'){
                Kc++;
                Kr++;
            }
        }else if(input == "R"){
            if(Kc + 1 == Rc && Kr == Rr){
                if(Rc + 1 <= 'H'){
                    Kc++;
                    Rc++;
                }
            }else if(Kc + 1 <= 'H'){
                Kc++;
            }
        }else if(input == "RB"){
            if(Kc + 1 == Rc && Kr - 1 == Rr){
                if(Rc + 1 <= 'H' && Rr - 1 >= '1'){
                    Kc++;
                    Kr--;
                    Rc++;
                    Rr--;
                }
            }else if(Kc + 1 <= 'H' && Kr - 1 >= '1'){
                Kc++;
                Kr--;
            }
        }else if(input == "B"){
            if(Kc == Rc && Kr - 1 == Rr){
                if(Rr - 1 >= '1'){
                    Kr--;
                    Rr--;
                }
            }else if(Kr - 1 >= '1'){
                Kr--;
            }
        }else if(input == "LB"){
            if(Kc - 1 == Rc && Kr - 1 == Rr){
                if(Rc - 1 >= 'A' && Rr - 1 >= '1'){
                    Kc--;
                    Kr--;
                    Rc--;
                    Rr--;
                }
            }else if(Kc - 1 >= 'A' && Kr - 1 >= '1'){
                Kc--;
                Kr--;
            }
        }
    }

    cout << Kc << Kr << "\n";
    cout << Rc << Rr << "\n";

    return 0;
}
```