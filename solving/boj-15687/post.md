[문제 바로가기](https://boj.kr/15687)

```c++
#include <bits/stdc++.h>

using namespace std;

class Rectangle{
private:
    int height;
    int width;

public:
    Rectangle(int w, int h){
        this->width = w;
        this->height = h;
    }

    int get_width() const{
        return this->width;
    }

    int get_height() const{
        return this->height;
    }

    void set_width(int w){
        if(w > 0 && w <= 1000){
            this->width = w;
        }
    }

    void set_height(int h){
        if(h > 0 && h <= 2000){
            this->height = h;
        }
    }

    int area() const{
        return height * width;
    }

    int perimeter() const{
        return 2 * (height + width);
    }

    bool is_square() const{
        return (height == width);
    }
};

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cout << "Hello, World!" << "\n";

    return 0;
}
```