[문제 바로가기](https://boj.kr/5397)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string password;
        cin >> password;

        list<char> result;
        auto current = result.begin();
        for(int j = 0; j < password.length(); j++){
            if(password[j] == '<'){
                if(current != result.begin()){
                    current--;
                }
            }else if(password[j] == '>'){
                if(current != result.end()){
                    current++;
                }
            }else if(password[j] == '-'){
                if(current != result.begin()){
                    auto temp = current;
                    current--;
                    result.erase(current);
                    current = temp;
                }
                
            }else{
                result.insert(current, password[j]);
            }
        }

        for(auto j = result.begin(); j != result.end(); j++){
            cout << *j;
        }
        cout << "\n";
    }
}
```