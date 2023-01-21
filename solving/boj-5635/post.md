[문제 바로가기](https://boj.kr/5635)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    string name;
    int d;
    int m;
    int y;
}student;

bool comp(student s1, student s2){
    if(s1.y == s2.y){
        if(s1.m == s2.m){
            return (s1.d < s2.d);
        }else{
            return (s1.m < s2.m);
        }
    }else{
        return (s1.y < s2.y);
    }
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<student> birth;
    for(int i = 0; i < N; i++){
        string name;
        int d, m, y;
        cin >> name >> d >> m >> y;
        birth.push_back({name, d, m, y});
    }

    sort(birth.begin(), birth.end(), comp);

    cout << birth[N - 1].name << "\n";
    cout << birth[0].name << "\n";

    return 0;
}
```