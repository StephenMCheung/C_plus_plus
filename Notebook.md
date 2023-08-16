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
