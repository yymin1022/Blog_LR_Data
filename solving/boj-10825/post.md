[문제 바로가기](https://boj.kr/10825)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    string name;
    int ko;
    int en;
    int math;
} score;

bool cmp(score s1, score s2){
    if(s1.ko == s2.ko){
        if(s1.en == s2.en){
            if(s1.math == s2.math){
                return (s1.name < s2.name);
            }else{
                return (s1.math > s2.math);
            }
        }else{
            return (s1.en < s2.en);
        }
    }else{
        return (s1.ko > s2.ko);
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<score> arr;
    for(int i = 0; i < N; i++){
        string name;
        int ko, en, math;
        cin >> name >> ko >> en >> math;
        arr.push_back({name, ko, en, math});
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < N; i++){
        cout << arr[i].name << "\n";
    }

    return 0;
}
``