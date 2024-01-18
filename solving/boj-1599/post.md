[문제 바로가기](https://boj.kr/1599)

```c++
#include  <bits/stdc++.h>

using namespace std;

string getWord(string input){
    string res;

    for(int i = 0; i < input.size(); i++){
        if(input[i] == 'n' && i + 1 < input.size() && input[i + 1] == 'g'){
            i++;
            res.push_back('l');
        }else if(input[i] == 'a'){
            res.push_back('a');
        }else if(input[i] == 'b'){
            res.push_back('b');
        }else if(input[i] == 'k'){
            res.push_back('c');
        }else if(input[i] == 'd'){
            res.push_back('d');
        }else if(input[i] == 'e'){
            res.push_back('e');
        }else if(input[i] == 'g'){
            res.push_back('f');
        }else if(input[i] == 'h'){
            res.push_back('g');
        }else if(input[i] == 'i'){
            res.push_back('h');
        }else if(input[i] == 'l'){
            res.push_back('i');
        }else if(input[i] == 'm'){
            res.push_back('j');
        }else if(input[i] == 'n'){
            res.push_back('k');
        }else if(input[i] == 'o'){
            res.push_back('m');
        }else if(input[i] == 'p'){
            res.push_back('n');
        }else if(input[i] == 'r'){
            res.push_back('o');
        }else if(input[i] == 's'){
            res.push_back('p');
        }else if(input[i] == 't'){
            res.push_back('q');
        }else if(input[i] == 'u'){
            res.push_back('r');
        }else if(input[i] == 'w'){
            res.push_back('s');
        }else if(input[i] == 'y') {
            res.push_back('t');
        }
    }

    return res;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<string, string>> arr;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        arr.push_back(make_pair(getWord(input), input));
    }

    sort(arr.begin(), arr.end());

    for(int i = 0; i < N; i++){
        cout << arr[i].second << "\n";
    }

    return 0;
}
```