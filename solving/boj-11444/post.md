[문제 바로가기](https://boj.kr/11444)

```c++
#include  <bits/stdc++.h>

using namespace std;

vector<vector<long long>> multiply(vector<vector<long long>>,vector<vector<long long>>);

long long N;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    vector<vector<long long>> answer = {{{0, 1}, {1, 0}}};
    vector<vector<long long>> temp = {{{1, 1}, {1, 0}}};
    for(long long i = N; i > 0; i /= 2){
        if(i % 2){
             answer = multiply(temp, answer);
        }

        temp = multiply(temp, temp);
    }

    cout << answer[0][0] << "\n";

    return 0;
}

vector<vector<long long>> multiply(vector<vector<long long>> a, vector<vector<long long>> b){
    vector<vector<long long>> temp(2, vector<long long>(2));

    for(int i = 0; i < 2; i++){
        for(int j = 0; j < 2; j++){
            for(int k = 0; k < 2; k++){
                temp[i][j] += a[i][k] * b[k][j];
            }

            temp[i][j] %= 1000000007;
        }
    }

    return temp;
}
```