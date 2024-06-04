[문제 바로가기](https://boj.kr/1380)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int T = 1;
    while(N){
        cin.ignore();

        vector<string> student;
        for(int i = 0; i < N; i++){
            string input;
            getline(cin, input);
            student.push_back(input);
        }

        map<int, bool> data;
        for(int i = 0; i < 2 * N - 1; i++){
            int A;
            string B;
            cin >> A >> B;
            if(data[A]){
                data[A] = false;
            }else{
                data[A] = true;
            }
        }

        for(auto iter = data.begin(); iter != data.end(); iter++){
            if(iter->second){
                cout << T << " ";
                cout << student[iter->first - 1] << "\n";
                break;
            }
        }

        cin >> N;
        T++;
    }

    return 0;
}

```
