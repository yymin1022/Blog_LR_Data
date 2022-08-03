[문제 바로가기](https://boj.kr/17214)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    string formula;
    cin >> formula;

    bool isFirst = false;
    int xIdx = 0;
    for(int i = 0; i < formula.size(); i++){
        if(formula[i] == 'x'){
            isFirst = true;
            xIdx = i;
            break;
        }
    }

    if(!isFirst){
        int num = stoi(formula);

        if(num == 0){
            cout << "W";
        }else if(num == 1){
            cout << "x+W";
        }else if(num == -1){
            cout << "-x+W";
        }else{
            cout << num << "x+W";
        }
    }else{
        string temp = "";
        for(int i = 0; i < xIdx; i++){
            temp += formula[i];
        }

        int num = stoi(temp) / 2;

        if(num == 1){
            cout << "xx";
        }else if(num == -1){
            cout << "-xx";
        }else{
            cout << num << "xx";
        }

        temp = "";
        for(int i = xIdx + 1; i < formula.size(); i++){
            temp += formula[i];
        }

        if(temp == ""){
            temp = "0";
        }

        num = stoi(temp);

        if(num == 0){
            cout << "+W";
        }else if(num == 1){
            cout << "+x+W";
        }else if(num == -1){
            cout << "-x+W";
        }else if(num > 0){
            cout << "+" << num << "x+W";
        }else{
            cout << num << "x+W";
        }
    }

    cout << "\n";

    return 0;
}
```