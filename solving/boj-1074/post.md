[문제 바로가기](https://boj.kr/1074)

```c++
#include <bits/stdc++.h>

using namespace std;

void search(int, int, int);

int N, r, c, cnt;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> r >> c;

    N = pow(2, N);

    search(0, 0, N);

    return 0;
}

void search(int x, int y, int size){
    if(size > 2){
        if(c < x + size / 2 && r < y + size / 2){
            search(x, y, size / 2);
        }else if(c >= x + size / 2 && r < y + size / 2){
            cnt += pow(size / 2, 2);
            search(x + size / 2, y, size / 2);
        }else if(c < x + size / 2 && r >= y + size / 2){
            cnt += 2 * pow(size / 2, 2);
            search(x, y + size / 2, size / 2);
        }else if(c >= x + size / 2 && r >= y + size / 2){
            cnt += 3 * pow(size / 2, 2);
            search(x + size / 2, y + size / 2, size / 2);
        }
    }else{
        if(x == c && y == r){
            cout << cnt << "\n";
            return;
        }
        cnt++;
        if(x + 1 == c && y == r){
            cout << cnt << "\n";
            return;
        }
        cnt++;
        if(x == c && y + 1 == r){
            cout << cnt << "\n";
            return;
        }
        cnt++;
        if(x + 1 == c && y + 1 == r){
            cout << cnt << "\n";
            return;
        }
        cnt++;
    }
}```