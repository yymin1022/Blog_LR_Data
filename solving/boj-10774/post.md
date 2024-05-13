[문제 바로가기](https://boj.kr/10774)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int J, A;
    cin >> J >> A;

    vector<char> arr(J + 1);
    for(int i = 1; i <= J; i++){
        cin >> arr[i];
    }

    int ans = 0;
    for(int i = 0; i < A; i++){
        char tag;
        int num;
        cin >> tag >> num;

        if(arr[num] == 'S'){
            if(tag == 'S'){
                ans++;
                arr[num] = 'X';
            }
        }else if(arr[num] == 'M'){
            if(tag == 'M' || tag == 'S'){
                ans++;
                arr[num] = 'X';
            }
        }else if(arr[num] == 'L'){
            if(tag == 'L' || tag == 'M' || tag == 'S'){
                ans++;
                arr[num] = 'X';
            }
        }
    }

    cout << ans << "\n";

    return 0;
}

```
