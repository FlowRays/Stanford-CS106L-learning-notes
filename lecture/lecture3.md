# Streams
## iostream
+ std::cin / std::cout:    
global constant object that you can get from `#include <iostream`
+ edge case of std::cin

```cpp
int age;
double time;
cin>>age>>time;     // input: 2.17
cout<<age<<endl;    // 2
cout<<time<<endl;   // 0.17
```

## getline
+ prototype:  
`std::getline(istream& stream, string& line);` 
+ usage:
    - `std::getline(cin,line); // istream`
    - `std::getline(fin,line); // ifstream`
+ edge case when mixed with cin:

```cpp
int age;
string s;
cin>>age;
cin.ignore();   // 忽略读入age后的\n，不然getline只能读入\n
getline(cin,s); // getline和cin混用需要谨慎
cout<<age<<endl;
cout<<s<<endl;
```

## fstream
+ file stream
+ `std::ofstream fileOut("out.txt",std::ios::app); // append mode`

## stringstream
+ To send data (in string form) to a stream, use `stream_name << data`
+ To extract data from a stream, use `stream_name >> data`, and the stream will try to convert a string to whatever type data is
+ Tip: be careful with the case below

```cpp
ostringstream oss("hello world");
cout<<oss.str()<<endl;  // hello world
// 读入会从头开始覆盖初始化的内容
oss<<"test";
cout<<oss.str()<<endl;  // testo world
// 在上一个读入的指针之后继续，而不会覆盖
oss<<"TEST test";
cout<<oss.str()<<endl; // testTEST test
```
