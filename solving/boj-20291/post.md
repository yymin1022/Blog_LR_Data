[문제 바로가기](https://boj.kr/20291)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> fileList;
    for(int i = 0; i < N; i++){
        string fileName;
        cin >> fileName;

        for(int j = 0; j < fileName.size(); j++){
            if(fileName[j] == '.'){
                string tmp = fileName.substr(j + 1, fileName.size() - j);
                fileList.push_back(tmp);
                break;
            }
        }
    }

    sort(fileList.begin(), fileList.end());

    map<string, int> file;
    for(int i = 0; i < fileList.size(); i++){
        file[fileList[i]]++;
    }

    for(auto iter = file.begin(); iter != file.end(); iter++){
        cout << iter->first << " ";
        cout << iter->second << "\n";
    }

    return 0;
}
```