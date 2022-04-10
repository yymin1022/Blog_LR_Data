[문제 바로가기](https://boj.kr/1302)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    int maxCnt = 0;
    map<string, int> books;
    for(int i = 0; i < N; i++){
        string title;
        cin >> title;
        books[title]++;

        if(books[title] > maxCnt){
            maxCnt = books[title];
        }
    }

    for(auto temp = books.begin(); temp != books.end(); temp++){
        if(temp->second == maxCnt){
            cout << temp->first << "\n";
            break;
        }
    }
}
```