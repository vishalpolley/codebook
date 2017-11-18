## strchr() in C++

[Programiz](https://www.programiz.com/cpp-programming/library-function/cstring/strchr)

<p align="center">
<img src="https://user-images.githubusercontent.com/20622980/32978736-150a47ca-cc6e-11e7-9ae3-db58506679b2.png">
</p>

```cpp
#include <cstring>
#include <iostream>

using namespace std;

int main()
{
    string str = "Programming is easy.";
    char ch = 'r';

    if (strchr(str.c_str(), ch))
        cout << ch << " is present \"" << str.c_str() << "\"";
    else
        cout << ch << " is not present \"" << str << "\"";

    return 0;
}

```
