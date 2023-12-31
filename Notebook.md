### 第 4 章  复合类型
#### 4.1  数组
数组是一种数据格式，能够存储多个同类型的值。要创建数组，可以使用声明语句。数组声明要指出以下三点：
- 存储在给个元素中的值的类型；
- 数组名；
- 数组中的元素数。
  
声明数组的通用格式如下：  
typeName arrayName[arraySize];

程序清单4.1 arrayone.cpp  
  
    #include <iostream>
    int main()
    {
        using namesapce std;
        int yams[3];
        yams[0] = 7;
        yams[1] = 8;
        yams[2] = 6;

        int yamcosts[3] = {20, 30, 5};
        cout << "Total yams = " << yams[0] + yams[1] + yams[2] << endl;
        cout << "The package with " << yams[1] << " yams costs " << yamcosts[1] << " cents peryam.\n";
        int total = yams[0] * yamcosts[0] + yams[1] * yamcosts[1];
        total = total + yams[2] * yamcsots[2];
        cout << "The total yam expense is " << total << " cents.\n";

        return 0
    }

##### 数组初始化的规则

- 只有在定义数组时才能使用初始化，此后就不能使用了，也不能将一个数组赋给另一个数组；
- 初始化数组时，提供的值可以少于数组的元素个数；
- 如果只对数组的一部分进行初始化，则编译器将把其他元素设置为0；
- 如果初始化数组时方括号为空，则编译器将计算元素的个数。
- 
##### C++11 数组初始化方法

- 初始化数组时，可省略等号；
- 可不在打括号内包含任何东西，从而将所有元素设置为0；
- 列表初始化禁止缩窄转换

#### 4.2 字符串  
C++处理字符串的方式有两种。第一种来自C语言，称为C风格字符串。例如，  
    char cat[8] = {'f', 'a', 't', 'e', 's', 's', 'a', '\0'};  
字符串常量或字符串字面值：  
    char fish[] = "Bubbles";  
注：在确定存储字符串所需的最短数组时，别忘了将结尾的空字符计算在内。

##### 拼接字符串常量  
C++允许拼接字符串字面值，即将两个用引号括起来的字符串合并为一个。  

##### 在数组中使用字符串   
要将字符串存储到数组中，最常用的方法有两种：将数组初始化为字符串常量；将键盘或文件输入读入到数组中。   

        #include <iostream>
        #include <cstring>
        int main()
        {
            using namespace std;
            const int Size = 15;
            char name1[Size];
            char name2[Size] = "C++owboy";

            cout << "Howdy! I'm " << name2 << "! What's your name?\n"
            return 0;
        }

##### 字符串输入  
cin使用空白（空格、制表符和换行符）来确定字符串的结束位置，这意味着cin在获取字符数组输入时只读取一个单词。   

##### 每次读取一行字符串输入   
- 面向行的输入：getline()  
- 面向行的输入：get()

##### 混合输入字符串和数字  

#### 4.3 string类简介  
要使用string类，必须在程序中包含头文件string。  

        #include <iostream>
        #include <string>
        int main()
        {
            using namespace std;
            char charr1[20];
            char charr2[20] = "jaguar";
            string str1;
            string str2 = "panther";

            cin >> charr1;
            cout << charr1 << endl;
            cin >> str1;
            cout << str1 << endl;
            return 0;
        }

##### 赋值、拼接和附加   
可以使用运算符+将两个string对象合并起来

##### string类的其他操作   
使用函数strcpy()将字符串赋值到字符数组中，使用函数strcat()将字符串附加到字符数组末尾。  

#### 4.4 结构简介  

        struct inflatable
        {
            char name[20];
            float volume;
            double price;
        }

程序清单4.11 structur.cpp   

        #include <iostream>
        struct inflatable
        {
            char name[20];
            float volume;
            double price;
        }
        int main()
        {
            using namespace std;
            inflatable guest = 
            { 
                "Glorious Gloria",
                1.88,
                29.99
            };
            cout << guest.name <<endl;
            return 0;
        }

可以同时完成定义结构和创建结构变量的工作，只需要将变量名放在结束括号的后面即可：  

        struct perks
        {
            int key_number;
            char car[12];
        }mr_smith, ms_jones;

#### 4.5 共用体  
共用体是一种数据格式，能够存储不同的数据类型，但是只能同时存储其中的一种类型。也就是说，结构体可以存储int、long和double，共用体只能存储int、long或double。

    union one4all
    {
        int int_val;
        long long_val;
        double double_val;
    };

公用体的用途之一是，当数据项使用两种或更多种俄式时，可节省空间。  
匿名共用体没有名称，其成员将成为位于相同地址处的便变量。

#### 4.6 枚举

    enum spectrum {red, orange, yellow, green, blue, violet, indigo, ultraviolet};

#### 4.7 指针和自由存储空间

指针是一个变量，其存储的是值的内存地址。  

    int a = 100;
    int* p = &a;
    *p
    
##### 使用new来分配内存

    int* p = new int;
    *p = 100;
    delete p;

##### 使用new来创建动态数组

    int* p = new int[10];
    delete [] p;

#### 4.8 指针、数组和指针算数

将整数变量加1后，其值将增加1；但将指针变量加1后，增加的量等于它指向的类型的字节数。  
C++将数组名解释为数组第一个元素的地址。

#### 4.9 类型组合

数组、结构体和指针的组合......

#### 4.10 数组的替代品

##### 模板类vector  
    #include <vector>
    ...
    using namespace std;
    vector<int> vi;
    int n;
    cin >> n;
    vector<double> vd(n);

##### 模板类array   
    #include <array>
    ...
    using namespace std;
    array<int, 5> ai;
    array<double, 4> ad = {1.2, 2.1, 3.43, 4.3};

##### 比较数组、vector和array

- 三者都可使用标准数组表示法来访问各个元素；
- array对象和数组存储在相同的内存区域（栈）中，而vector存储在自由存储区域或堆中；
- 可以将一个array对象赋值给另一个array对象，而对于数组，必须逐元素赋值数据。
