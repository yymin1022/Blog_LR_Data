[문제 바로가기](https://boj.kr/2447)

```c++
#include <bits/stdc++.h>

using namespace std;

void printStar(int, int, int);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            printStar(i, j, N);
        }

        cout << "\n";
    }

    return 0;
}

void printStar(int x, int y, int tempN){
    string printStr = " ";
    if(x / tempN % 3 == 1 && y / tempN % 3 == 1){
        cout << " ";
    }else if(tempN / 3 == 0){
        cout << "*";
    }else{
        printStar(x, y, tempN / 3);
    }
}```