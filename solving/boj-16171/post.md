[문제 바로가기](https://boj.kr/16171)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string book, word;
    cin >> book >> word;

    string newBook;
    for(int i = 0; i < book.size(); i++){
        if(book[i] - '0' > 10){
            newBook += book[i];
        }
    }

    if(newBook.find(word) != string::npos){
        cout << 1 <<"\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}```