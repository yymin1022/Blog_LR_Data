[문제 바로가기](https://boj.kr/1644)

```c++
#include <bits/stdc++.h>

using namespace std;

void getPrime();

int N;
vector<int> prime;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    getPrime();

    int cnt = 0;
    int left = 0;
    int right = 0;
    int sum = 2;
    while(right < prime.size()){
        if(sum == N){
            cnt++;
        }

        if(sum < N){
            right++;
            sum += prime[right];
        }else{
            sum -= prime[left];
            left++;
        }
    }

    cout << cnt << "\n";

    return 0;
}

void getPrime() {
    vector<bool> temp(N);
    for(int i = 2; i * i <= N; i++){
        if(!temp[i]){
            for(int j = i * i; j <= N; j += i){
                temp[j] = true;
            }
        }
    }

    for(int i = 2; i <= N; i++){
        if(!temp[i]){
            prime.push_back(i);
        }
    }
}```