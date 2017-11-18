## What does "const string&" in C++ mean?

[Quora](https://www.quora.com/What-does-const-string-in-C++-mean)

<p align="center">
<img src="https://user-images.githubusercontent.com/20622980/32978334-21a51558-cc66-11e7-9eb0-6937fba08c6f.jpg">
</p>

```cpp
void passCopy(string a)
{
    a = "changed";
}
 
void passRef(string& a)
{
   a = "changed";
}
 
void passConstRef(const string& a)
{
  a = "chnaged 2";  // compilation error, since it is a read only reference.
} 
 
int main()
{
      string a = "str";
      cout << a;  //prints "str"
      
      passCopy(a);
      cout << a; // still prints "str", as we have made changes on copy not 
                        //on original code.
 
      passRef(a);
      cout << a; // prints "changed" , as we passed the original (reference).
 
      passConstRef(a);  //throws error.
      //because we are trying to edit the read only reference.
 
      return 0;
}      
```

```cpp
#include<iostream>
using namespace std;

string g_value;
void callback()
{    
  g_value = "blue";
}
void ProcessStringByRef(string &s)
{    
  callback(); 
  std::cout << s << "\n";
}
void ProcessStringByValue(const string s)
{    
  callback();
  std::cout << s << "\n";
}
int main()
{
  g_value = "red";
  ProcessStringByRef(g_value);
  g_value = "red";
  ProcessStringByValue(g_value);
}

```
