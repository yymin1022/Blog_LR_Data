[문제 바로가기](https://boj.kr/2535)

```c++
#include <bits/stdc++.h>

using namespace std;

typedef struct{
    int country;
    int number;
    int score;
} student;

bool compareStudent(student s1, student s2){
    if(s1.score != s2.score){
        return s1.score > s2.score;
    }

    if(s1.country != s2.country){
        return s1.country < s2.country;
    }

    return s1.number < s2.number;
}

int cnt[101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<student> arr;
    for(int i = 0; i < N; i++){
        int country, number, score;
        cin >> country >> number >> score;
        arr.push_back(student{country, number, score});
    }

    sort(arr.begin(), arr.end(), compareStudent);

    vector<student> ans;
    for(int i = 0; ans.size() <= 3; i++){
        int cur = arr[i].country;

        if(cnt[cur] < 2){
            ans.push_back(arr[i]);
            cnt[cur]++;
        }
    }

    for(int i = 0; i < 3; i++){
        cout << ans[i].country << " " << ans[i].number << "\n";
    }

    return 0;
}
```