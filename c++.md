



## c++

### 1.c++基础

#### 1.1变量

变量存在的意义在于我们方便操作数据，管理内存空间；

变量创建语法：数据类型	数据名 = 变量初始值；

```c++
#include<iostream>

using namespace std;

int main()
{
	int a = 10;
	cout << "a = " << a << endl;
	system("pause");
	return 0;
}
```

#### 1.2常量

C++常量定义方式：

1. #define宏常量：`#define 常量名 常量值`
2. const修饰的变量：`const 数据类型 常量名 = 常量值`

```c++
#include<iostream>

using namespace std;

#define day 7

int main()
{
	cout << "一周有" << day << "天" <<  endl;
	//day = 8 报错，宏常量不可修改
	//const修饰变量
	const int month = 12;
	cout << "一年有" << month << "个月" << endl;
	//month = 13 报错 常量不可修改

	system("pause");
	return 0;
}
```

#### 1.3关键字

1. 标识符不能是关键字
2. 标识符只能由字母、数字、下划线组成
3. 第一个字符必须为字母或者下划线
4. 标识符中字母区分大小写

### 2.数据类型

数据类型的意义：给变量分配合适的内存空间；

short 2B、int 4B、long 4B、long long 8B

#### 2.1整型

```c++
#include<iostream>

using namespace std;

int main()
{
	short num1 = 10;
	int num2 = 10;
	long num3 = 10;
	long long num4 = 10;

	cout << "num1 = " << num1 << endl;
	cout << "num2 = " << num2 << endl;
	cout << "num3 = " << num3 << endl;
	cout << "num4 = " << num4 << endl;
    
    return 0;
}
```

#### 2.2sizeof关键字

利用sizeof关键字可以统计数据类型所在内存大小：`sizeof(数据类型/变量)`

```c++
#include<iostream>
using namespace std;

int main()
{
	short num1 = 10;
	cout << "short占用内存空间为：" << sizeof(num1) << endl;

	int num2 = 10;
	cout << "short占用内存空间为：" << sizeof(num2) << endl;
	long num3 = 10;
	cout << "short占用内存空间为：" << sizeof(num3) << endl;
	long long num4 = 10;
	cout << "short占用内存空间为：" << sizeof(num4) << endl;

	system("pause");
	return 0;
}
```

#### 2.3浮点型

float 单精度 4B double双精度 8B

```c++
#include<iostream>

using namespace std;

int main()
{
	float f1 = 3.1415926f;//默认把小数当成float，加一个f表示存为单精度
	double d1 = 3.1415926;//最多表示6位有效数字
	cout << "f1 = " << f1 << endl;
	cout << "d1 = " << d1 << endl;
	system("pause");
	return 0;
}
```

#### 2.4字符型

字符型变量用于显示单个字符 `char ch = 'a'`

字符型变量只占一个字节

字符型变量本身并不是把字符本身放到内存中存储，而是将对应的ASCII码放入存储单元；

```c++
#include<iostream>

using namespace std;

int main()
{
	char ch = 'a';//创建字符型变量要用单引号，只能放一个字符
	cout << ch << endl;
	cout << sizeof(char) << endl;

	system("pause");
	return 0;
}
```

#### 2.5转义字符

用于表示一些不能显示出来的ASCII字符；

常用转移字符：`\n换行符 \\反斜杠  \t水平制表符`

#### 2.6字符串型

```c++
#include<iostream>
#include<string>

using namespace std;

int main()
{
	char str1[] = "hello world";//中括号 双引号
	cout << str1 << endl;

	string str2 = "hello world";
	cout << str2 << endl;

	return 0;
}
```

#### 2.7bool类型

bool类型占一个字节；

### 3.运算符

#### 3.1算术运算符

```c++
#include<iostream>

using namespace std;

int main()
{

	int a1 = 10;
	int b1 = 3;
	cout << a1 + b1 << endl;
	cout << a1 - b1 << endl;
	cout << a1 * b1 << endl;
	cout << a1 / b1 << endl;//a b为int型，除法结果为整数


	double d1 = 0.5;
	double d2 = 0.22;
	cout << d1 / d2 << endl;

	//取模运算 求余数
	cout << a1 % b1 << endl;

	//前置递增
	int a = 10;
	int b = ++a;//b=11

	//后置递增
	int c = 10;
	int d = c++;//d=10
	
	//前置和后置的区别
	//前置递增，先让变量进行+1 然后进行表达式运算
	int a2 = 10;
	int b2 = ++a2 * 10;
	cout << "a2=" << a2 << endl;
	cout << "b2=" << b2 << endl;

	//后置递增，先进行表达式运算，后让变量+1
	int a3 = 10;
	int b3 = a3++ * 10;
	cout << "a3=" << a3 << endl;
	cout << "b3=" << b3 << endl;


	system("pause");
	return 0;
}
```

#### 3.2赋值运算符

```c++
#include<iostream>

using namespace std;

int main()
{
	//赋值运算符

	//=
	int a = 10;
	a = 100;
	cout << "a=" << a << endl;
	//+=
	int b = 10;
	b += 2;
	cout << "b=" << b << endl;
	//-=
	int c = 10;
	c -= 2;
	cout << "c=" << c << endl;
	//*=
	int d = 10;
	d *= 2;
	cout << "d=" << d << endl;
	// /=
	int e = 10;
	e /= 2;
	cout << "e=" << e << endl;

	//%=
	int f = 10;
	f %= 2;
	cout << "f=" << f << endl;
}
```

#### 3.3比较运算符



#### 3.4逻辑运算符



### 4.程序流程结构

顺序结构、选择结构、循环结构

#### 4.1选择结构

##### 4.1.1if语句

单行if

```c++
#include<iostream>

using namespace std;

int main1()
{
	int score = 0;

	cout << "请输入分数：" << endl;
	cin >> score;
	if (score >= 600)
		cout << "恭喜你考上一本！！" << endl;
	return 0;
}
```

多行if

```c++
#include<iostream>

using namespace std;

int main()
{
	int score = 0;
	cout << "请输入分数：" << endl;
	cin >> score;
	if (score >= 600)
		cout << "恭喜你考上一本！！" << endl;
	else
		cout << "没有考上一本" << endl;
	system("pause");
	return 0;
}
```

多条件if

```c++
#include<iostream>

using namespace std;

int main()
{
	int score = 0;

	cout << "请输入你的分数：" << endl;
	cin >> score;

	cout << "您输入的分数为：" << score << endl;

	if (score>=600)
	{
		cout << "恭喜您考上一本大学！！！" << endl;
	}
	else if (score>=500)
	{
		cout << "恭喜您考上二本大学！！" << endl;
	}
	else if (score >= 400)
	{
		cout << "恭喜您考生三本大学！" << endl;
	}
	else
	{
		cout << "很遗憾您未考上本科···" << endl;
	}

	system("pause");
	return 0;
}
```

嵌套if语句

```c++
#include<iostream>

using namespace std;

int main()
{
	int score = 0;

	cout << "请输入你的分数：" << endl;
	cin >> score;

	cout << "你的分数为：" << score << endl;
	//如果大于600 一本
	if (score>=600)
	{
		if (score >= 700)
		{
			cout << "恭喜你考上北大！！！" << endl;
		}
		else if (score>=650)
		{
			cout << "恭喜您考上清华！！！" << endl;
		}
		else
		{
			cout << "恭喜你考入人大" << endl;;
		}
	}
	else if (score >= 500)
	{
		cout << "恭喜您考上二本" << endl;
	}
	else if (score >= 400)
	{
		cout << "恭喜你考上三本" << endl;
	}
	else
	{
		cout << "很遗憾您未考上本科" << endl;
	}

	system("pause");
	return 0;
}
```

##### 案例

```c++
#include<iostream>

using namespace std;

int main()
{
	int num1 = 0;
	int num2 = 0;
	int num3 = 0;

	//输入三只小猪重量
	cout << "请输入小猪A的体重：" << endl;
	cin >> num1;
	cout << "请输入小猪B的体重：" << endl;
	cin >> num2;
	cout << "请输入小猪C的体重：" << endl;
	cin >> num3;
	cout << "小猪A的体重：" << num1<<endl;
	cout << "小猪B的体重：" <<num2<< endl;
	cout << "小猪C的体重：" <<num3<< endl;

	
	if (num1 > num2)
	{
		if (num1 > num3)
		{
			cout << "小猪A最重" << endl;
		}
		else
		{
			cout << "小猪C最重" << endl;
		}
	}
	else
	{
		if (num2 > num3)
		{
			cout << "小猪B最重" << endl;
		}
		else
		{
			cout << "小猪C最重" << endl;
		}
	}

	system("pause");
	return 0;

}
```

##### 4.1.2三目运算符

c = a > b ? a : b

表达式为真则返回a的值，为假则返回b的值；

##### 4.1.3swtich语句

```
#include<iostream>

using namespace std;

int main()
{
	int score = 0;
	cout << "请输入分数：" << endl;

	cin >> score;

	switch (score)
	{
		case 100:
			cout << "满分" << endl;
			break;
		case 85:
			cout << "优秀" << endl;
			break;
	}

	system("pause");
	return 0;
}
```

#### 4.2循环结构

##### 4.2.1while循环语句

```c++
#include<iostream>

using namespace std;

int main()
{
	int num = 0;
	while (num < 10)
	{
		num++;
		cout << num << endl;
	}

	system("pause");
	return 0;
}
```

 ```c++
 //猜数字游戏
 #include<iostream>
 #include<ctime>
 using namespace std;
 
 int main()
 {
 	//添加随机数种子，防止每次随机数都一样
 	srand((unsigned int)time(NULL));
 	//1系统生成随机数
 	//rand()%100  //生成一个0-99的随机数
 	int num = rand() % 100 + 1;
 
 	//2玩家进行猜测
 	int val = 0;
 	while (1)
 	{
 		cin >> val;
 		if (val > num)
 		{
 			cout << "大了" << endl;
 		}
 		else if (val < num)
 		{
 			cout << "小了" << endl;
 		}
 		else
 		{
 			cout << "猜对了" << endl;
 			break;
 		}
 	}
 	//3判断玩家的猜测
 	
 	system("pause");
 	return 0;
 }
 ```

##### 4.2.2do...while循环语句

```c++
#include<iostream>

using namespace std;

int main()
{
	int num = 0;

	do {
		cout << num << endl;
		num++;
	} while (num < 10);
	return 0;
}
```

水仙花数：一个三位数，每个位上的数字的3次幂之和等于它本身

```c++
#include<iostream>

using namespace std;

int main()
{
	int num = 100;
	
	do {
		int a = 0;
		int b = 0;
		int c = 0;
		 a = num % 10;
		 b = num / 10 % 10;
		 c = num / 100;
		if (num == a*a*a + b*b*b + c*c*c)
		{
			cout << num << endl;
		}
		num++;
	} while (num<1000);
	system("pause");
	return 0;
}
```

##### 4.2.3for循环语句

```c++
#include<iostream>

using namespace std;

int main()
{
	for (int i = 0; i < 10; i++)
	{
		cout << i << endl;
	}

	system("pause");
	return 0;
}
```

### 5.数组

#### 5.1一维数组

数组特点：放在一块连续的内存空间中，数组中每个元素都是相同的数据类型；

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[5] = {10,20,30,40,50};
	//arr[0] = 10;
	//arr[1] = 20;
	//arr[2] = 30;
	//arr[3] = 40;
	//arr[4] = 50;

	cout << arr[0] << endl;
	return 0;
}
```

冒泡排序：

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[9] = { 4,2,8,0,5,7,1,3,9 };
	cout << "排序前：" << endl;
	for (int i = 0; i < 9; i++)
	{
		cout << arr[i] << " ";
	}
	cout << endl;
	for (int i = 0; i < 9 - 1; i++)
	{
		for (int j = 0; j < 9 - i - 1; j++)
		{
			if (arr[j] > arr[j + 1])
			{
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}

	cout << "排序后：" << endl;
	for (int i = 0; i < 9; i++)
	{
		cout << arr[i] << " ";
	}

	system("pause");
	return 0;

}
```

#### 5.2二维数组

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[2][3] = {
		{1,2,3},
		{4,5,6}
	};//{1,2,3,4,5,6}
	for (int i = 0; i < 2; i++)
	{
		for (int j = 0; j < 3; j++)
		{
			cout << arr[i][j] << endl;
		}
	}
	system("pause");
	return 0;
}
```

### 6.函数

#### 6.1语法

```
返回值类型 函数名（参数列表）
{
	函数体语句
	
	return 表达式
}
```

#### 6.2函数调用

```c++
#include<iostream>

using namespace std;

int add(int num1, int num2)//定义时没有实际参数值，为形参
{
	int sum = num1 + num2;
	return sum;
}

int main()
{
	int a = 0;
	int b = 0;
	cin >> a >> b;
	cout << add(a, b) << endl;//调用函数时传入实际参数，为实参

	system("pause");
	return 0;
}
```

#### 6.3值传递

```c++
#include<iostream>

using namespace std;

void swap(int num1, int num2)//不需要返回值，使用void
{
	cout << "交换前：" << num1 << num2 << endl;
	int temp = num1;
	num1 = num2;
	num2 = temp;
	cout << "交换后：" << num1 << num2 << endl;
}

int main()
{
	int a  = 0;
	int b = 0;
	cin >> a >> b;
	swap(a, b);

	system("pause");
	return 0;

}
```

#### 6.4函数形式

```c++
#include<iostream>

using namespace std;

//无参数无返回值
void test01()
{
	cout << "this is test01" << endl;
}

//有参数无返回值
void test02(int a)
{
	cout << "this is test02 a=" << a << endl;
}

//无参数有返回值
int test03()
{
	cout << "this is test03" << endl;
	return 100;
}

//有参数啊有返回值
int test04(int num1)
{
	return num1 - 1;
}
```

#### 6.5函数声明

```c++
#include<iostream>

using namespace std;

//函数声明，可以把函数定义放在main函数后面，提前告诉编译器函数存在
//声明可以多次，但定义只能一次
int max(int a, int b);

int main()
{
	int a = 10;
	int b = 20;
	cout << max(a, b) << endl;

	system("pause");
	return 0;
}

int max(int a, int b)
{
	return a > b ? a : b;
}
```

#### 6.6函数分文件编写

swap.h

```c++
#pragma once
#include<iostream>
using namespace std;
//函数声明
void swap1(int num1, int num2);
```

swap.cpp

```c++
#include<iostream>
#include"swap.h"
using namespace std;



void swap1(int num1, int num2)
{
	cout << "交换前：" << num1 << num2 << endl;
	int temp = num1;
	num1 = num2;
	num2 = temp;
	cout << "交换后：" << num1 << num2 << endl;
}

int main()
{
	int a = 1;
	int b = 2;
	swap1(a, b);
}
```

### 7.指针

#### 7.1指针的定义及应用

指针：记录变量地址

```c++
#include<iostream>

using namespace std;

int main()
{
	//定义指针
	int a = 10;

	//指针定义语法
	int* p;
	p = &a;
	cout << "a的地址为：" << &a << endl;
	cout << "指针p为：" << p << endl;

	//使用指针
	//可以通过解引用方式来寻找指针指向的内存
	//指针前加 * 代表解引用，找到指针指向的内存中的数据
	*p = 1000;
	cout << a << endl;

	system("pause");
	return 0;
}
```

#### 7.2指针所占内存空间

```c++
#include<iostream>

using namespace std;

int main()
{
	int a = 10;

	int* p = &a;
	//在32位操作系统下，指针占4B
	//在64位操作系统下，指针占8B
	cout << "sizeof(int *) = " << sizeof(int *) << endl;
	cout << "sizeof(float *) = " << sizeof(float *) << endl;
	cout << "sizeof(double *) = " << sizeof(double *) << endl;
	cout << "sizeof(char *) = " << sizeof(char *) << endl;

	system("pause");
	return 0;
}
```

#### 7.3空指针和野指针

空指针：指针变量指向内存中编号为0的空间；用于初始化指针变量；空指针指向的内存不可以访问；

```c++
#include<iostream>

using namespace std;

int main()
{
	//空指针用于指针变量进行初始化
	int* p = NULL;
	//空指针不可进行访问
	*p = 100;//运行出错不可以访问

	system("pause");
	return 0;
}
```

野指针：指向非法内存空间；

#### 7.4const修饰指针

```c++
#include<iostream>
using namespace std;

int main()
{
	//const int *p = &a 常量指针
	//指针指向可以修改，但指针指向的值不可以修改
	int a = 10;
	int b = 9;
	const int* p = &a;
	//不能修改a的值，但可以让指针指向b

	//int const *p = &a 指针常量
	//指针的指向不可以修改，但是指针指向的值可以改
	int a = 10;
	int b = 9;
	int const* p = &a;
	//可以修改a的值，但是不能让指针指向b

	//const int * const p = &a既修饰指针又修饰常量
	//指针的指向和指针指向的值都不能修改
	int a = 10;
	int b = 9;
	const int * const p = &a;
	//既不能修改a的值，又不能让p指向b
}
```

#### 7.5利用指针访问数组

```c++
#include<iostream>
using namespace std;

int main()
{
	int arr[10] = { 1,2,3,4,5,6,7,8,9,0 };

	cout << "第一个元素为" << arr[0] << endl;
	//int * p = arr;
	//cout << "利用指针访问第一个元素：" << *p << endl;
	//p++;
	//cout << "利用指针访问第二个元素：" << *p << endl;
	
	int * p2 = arr;
	for (int i = 0; i < 10; i++)
	{
		//cout << arr[i] << endl;
		cout << *p2 << endl;
		p2++;
	}

	system("pause");
	return 0;
}
```

### 8.结构体

#### 8.1结构体定义与使用

```c++
#include<iostream>
#include<cstring>
using namespace std;

struct Student
{
	string name;
	int age;
	int score;
}s3;//定义结构体时顺便创建结构体变量

int main()
{
	//通过学生类型创建具体学生
	//struct Student s1
	struct Student s1;
	s1.name = "张三";
	s1.age = 18;
	s1.score = 100;
	cout << "姓名：" << s1.name << "年龄：" << s1.age << "分数：" << s1.score << endl;

	//struct Student s2={...}
	struct Student s2 = { "李四",19,80 };
	cout << "姓名：" << s2.name << "年龄：" << s2.age << "分数：" << s2.score << endl;

	//d定义结构体时顺便创建结构体变量
	s3.name = "王五";
	s3.age = 20;
	s3.score = 10;
	cout << "姓名：" << s3.name << "年龄：" << s3.age << "分数：" << s3.score << endl;

	system("pause");
	return 0;
}	
```

#### 8.2结构体数组

将自定义结构体放到数组方便维护

```c++
#include<iostream>
#include<string>
using namespace std;

//定义结构体
struct Student
{
	string name;
	int age;
	int score;
};

int main()
{
	//创建结构体数组
	struct Student stuArr[3] = {
		{"张三",18,100},
		{"李四",20,90},
		{"王五",21,80}
	};
	stuArr[2].age = 19;
	for (int i = 0; i < 3; i++)
	{
		cout << "姓名：" << stuArr[i].name
			<< "年龄：" << stuArr[i].age
			<< "分数：" << stuArr[i].score << endl;
	}
	system("pause");
	return 0;
}
```

#### 8.3结构体指针

```c++
#include<iostream>
#include<string>
using namespace std;

//结构体指针
struct Student1
{
	string name;
	int age;
	int score;
};

int main()
{
	//创建学生结构体变量
	struct Student1 s = { "张三",18,100 };
	//通过指针指向结构体变量
	Student1* p = &s;
	//通过指针访问结构体数据
	cout << "姓名：" <<p->name
		<< "年龄：" << p->age
		<< "分数：" << p->score << endl;
	system("pause");
	return 0;
}
```

#### 8.4结构体嵌套结构体

结构体中的成员可以是另一个结构体；

```c++
#include<iostream>
#include<string>
using namespace std;

struct student
{
	string name;
	int age;
	int score;
};

struct teacher
{
	int id;
	string name;
	int age;
	struct student stu;
};

int main()
{
	teacher t;
	t.id = 10000;
	t.name = "老王";
	t.age = 50;
	t.stu.name = "小王";
	t.stu.age = 18;
	t.stu.score = 80;
	
	system("pause");
	return 0;
}
```

#### 8.5结构体做函数参数

```c++
#include<iostream>
#include<string>
using namespace std;

struct student1
{
	string name;
	int age;
	int score;
};

//值传递
void printstudent1(struct student1 s)
{
	s.score = 200;//不会改变实际参数
	cout << "子函数1中打印姓名" << s.name << "年龄：" << s.age << "分数：" << s.score << endl;
}
//地址传递
void printstudent2(struct student1 *p)
{
	p->score = 200;//会改变实际参数
	cout << "子函数2中打印姓名" << p->name << "年龄：" << p->age << "分数：" << p->score << endl;
}
int main()
{
	struct student1 s1;
	s1.name = "张三";
	s1.age = 20;
	s1.score = 80;

	printstudent1(s1);
	printstudent2(&s1);

	//cout << "main函数中打印姓名" << s1.name << "年龄：" << s1.age << "分数：" << s1.score << endl;
	system("pause");
	return 0;
}
```

#### 8.6结构体中const的使用场景

用const来防止误操作；

```
#include<iostream>
using namespace std;

struct student2
{
	string name;
	int age;
	int score;
};
//将函数中形参改为指针可以减少内存空间，而且不会复制一个新的副本
void printstudent2(const student2 *s)
{
	//s->age = 150;//地址传递会改变实参的值,加入const之后，不可修改结构体属性值
	cout << "姓名" << s->name << "年龄：" << s->age << "分数：" << s->score << endl;

}
int main()
{
	//创建结构体变量
	struct student2 s2 = { "张三",10,70 };
	//通过函数打印结构体变量信息
	printstudent2(&s2);

	system("pause");
	return 0;
}
```

#### 8.7结构体案例

1、

```c++
#include<iostream>
#include<string>
#include<ctime>
using namespace std;

struct students
{
	string sname;
	int score;
};

struct Teacher
{
	string tname;
	struct students sArr[5];
};

void allocateSpace(struct Teacher tArr[],int len)
{
	srand((unsigned int)time(NULL));
	string nameSeed = "ABCDE";
	//给老师开始赋值
	for (int i = 0; i < len; i++)
	{
		tArr[i].tname = "Teacher_";
		tArr[i].tname += nameSeed[i];
		//通过循环给美名老师带的学生赋值
		for (int j = 0; j < 5; j++)
		{
			tArr[i].sArr[j].sname = "Student_";
			tArr[i].sArr[j].sname += nameSeed[j];

			int random = rand() % 61 + 40;
			tArr[i].sArr[j].score = random;
		}
	}
}

void printInfo(struct Teacher tArr[], int len)
{
	for (int i = 0; i < len; i++)
	{
		cout << "老师姓名：" << tArr[i].tname << endl;

		for (int j = 0; j < 5; j++)
		{
			cout << "学生姓名：" << tArr[i].sArr[j].sname <<
				"考试分数：" << tArr[i].sArr[j].score << endl;
		}
	}
}
int main()
{
	//创建三名老师数组
	struct Teacher tArr[3];
	//通过函数给3名老师的信息赋值，并给老师所带学生赋值
	int len = sizeof(tArr) / sizeof(tArr[0]);
	allocateSpace(tArr, len);

	printInfo(tArr, len);

	system("pause");
	return 0;
}
```

2、

```c++
#include<iostream>
#include<string>

using namespace std;

struct Hero
{
	string name;
	int age;
	string sex;
};

void bubblesort(struct Hero heroArr[], int len)
{
	for (int i = 0; i < len - 1; i++)
	{
		for(int j=0;j<len-1-i;j++)
		{
			if (heroArr[j].age > heroArr[j + 1].age)
			{
				struct Hero temp = heroArr[j];
				heroArr[j] = heroArr[j + 1];
				heroArr[j + 1] = temp;
			}
		}
	}
}

void printhero(struct Hero heroArr[], int len)
{
	for (int i = 0; i < len; i++)
	{
		cout << "姓名：" << heroArr[i].name << "年龄：" << heroArr[i].age
			<< "性别：" << heroArr[i].sex << endl;
	}
}
int main()
{
	struct Hero heroArr[5] = {
		{"刘备",23,"男"},
		{"关羽",22,"男"},
		{"张飞",20,"男"},
		{"赵云",21,"男"},
		{"貂蝉",19,"女"}
	};

	int len = sizeof(heroArr) / sizeof(heroArr[0]);
	for (int i = 0; i < len; i++)
	{
		cout << "姓名：" << heroArr[i].name << "年龄：" << heroArr[i].age
			<< "性别：" << heroArr[i].sex << endl;
	}

	bubblesort(heroArr, len);
	printhero(heroArr, len);

	system("pause");
	return 0;
}
```

## c++核心

### 1.内存分析模型

内存划分四个区

- 代码区：存放函数体的二进制代码；
- 全局区：存放全局变量和静态变量；
- 栈区：编译器自动分配释放；
- 堆区：由程序员分配和释放；

### 2.引用

#### 2.1基本语法

作用：给一个变量起别名

操作别名和原名效果相同

```
#include<iostream>
using namespace std;

int main()
{
	//引用语法：数据类型 &别名=原名

	int a = 10;
	int& b = a;
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	
	b = 100;
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	system("pause");
	return 0;
}
```

#### 2.2**引用的注意事项**

- 引用必须初始化
- 引用初始化之后不可改变

```c++
#include<iostream>
using namespace std;

int main()
{
	int a = 10;
	//int& b;//错误，必须初始化
	int& b = a;
	int c = 20;
	
	b = c;//赋值操作，而非更改引用
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	cout << "c=" << c << endl;

	system("pause");
	return 0;
}
```

#### 2.3引用做函数参数

函数传参时，可以利用引用的技术让形参修饰实参；可以简化指针修改实参；

```c++
#include<iostream>
using namespace std;

void swap01(int a, int b)//值传递，形参改变，实参不改变
{
	int temp = a;
	a = b;
	b = temp;
}

void swap02(int* a, int* b)//地址传递，可改变实参
{
	int temp = *a;
	*a = *b;
	*b = temp;
}

void swap03(int& a, int& b)
{
	int temp = a;
	a = b;
	b = a;

}
int main()
{
	int a = 10;
	int b = 20;
	swap01(a,b);//值传递
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	swap02(&a,&b);//地址传递
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	swap03(a, b);//引用传递
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	system("pause");
	return 0;
}
```

#### 2.4引用做返回值

不要返回局部变量的引用

函数的调用可以作为左值；

```c++
#include<iostream>
using namespace std;

//不要返回局部变量的引用
int& test01()
{
	int a = 10;
	return a;
}
//函数的调用可以作为左值
int& test02()
{
	static int a = 10;//静态变量，存放在全局区
	return a;
}

int main()
{
	//int& ref = test01();
	//cout << "ref=" << ref << endl;//第一次结果正确，编译器做了保留
	//cout << "ref=" << ref << endl;//第二次结果错误

	int &ref2 = test02();
	cout << "ref2=" << ref2 << endl;//两次结果相同
	cout << "ref2=" << ref2 << endl;//两次结果相同

	test02() = 1000;//函数调用可以作为左值
	cout << "ref2=" << ref2 << endl;//1000
	system("pause");
	return 0;
}
```

#### 2.5引用的本质

引用的本质在c++内部实现就是一个指针常量；

#### 2.6常量引用

常量引用主要用来修饰形参，防止误操作；

```c++
#include<iostream>
using namespace std;

void showValue(const int& val)
{
	//val = 1000;//加上const后不可以修改参数，防止误操作
	cout << "val=" << val << endl;
}

int main()
{
	//int a = 10;
	//int& ref = a;//引用必须引一块合法的内存空间
	//加上const之后，编译器将代码修改int temp=10;const int & ref=temp;
	//const int& ref = 10;
	//ref = 20;变成常量后只读，不可修改

	int a = 10;
	showValue(a);
	system("pause");
	return 0;
}
```

### 3.函数提高

#### 3.1函数默认参数

语法：`返回值类型   函数名  （参数=默认值）{}`

```c++
#include<iostream>
using namespace std;

//int func(int a, int b = 20, int c = 30)
//{
//	return a + b + c;
//}
//注意：如果某个位置已经有了默认参数，
//那么从这个位置往后都必须有默认值
//int func(int a, int b = 20, int c)//出错c在b后面，b有c必须有
//{
//	return a + b + c;
//}
int func(int a, int b=10, int c=10)//有默认值的参数必须放在后面
{
	return a + b + c;
}
//如果函数声明有默认参数，那么函数实现就不能有默认参数
int fun2(int a = 10, int b = 10);

//int func2(int a = 10, int b = 10)//运行时会出错
//{
//	return a + b;
//}

int main()
{
	cout << func(10) << endl;//没传bc值，用默认值
	cout << func(10,30) << endl;//传了参数值，则用传参值
	cout << func(10,30,40) << endl;//传了参数值，则用传参值

	system("pause");
	return 0;
}
```

#### 3.2函数占位参数

形参列表里可以有占位参数，用来做占位，调用函数时必须填补该位置；

语法： 返回值类型 函数名 （数据类型）{}

#### 3.3函数重载

函数名可以相同，提高复用性；

函数重载满足条件：

- 同一个作用域下
- 函数名称相同
- 函数**参数类型不同或者个数不同或者顺序不同**

函数返回值类型不可作为重载条件；

```c++
#include<iostream>
using namespace std;

//函数重载
void funcc()
{
	cout << "func的调用1" << endl;
}

void funcc(int a)
{
	cout << "func的调用2" << endl;
}
void funcc(int a, double b)
{
	cout << "func的调用3" << endl;
}

void funcc(double b,int a)
{
	cout << "func的调用4" << endl;
}
int main()
{
	funcc();
	funcc(10);
	funcc(10,3.14);
	funcc(3.14,10);
	system("pause");
	return 0;
}
```

### 4.类和对象

c++面向对象三大特性：**封装、继承、多态**

#### 4.1封装

```c++
#include<iostream>
using namespace std;

const double PI = 3.14;
//设计圆类求周长
class Circle
{
public:
	//半径
	double r;
	//求周长函数
	double zc()
	{
		return 2 * PI * r;
	}
private:
	
};

int main()
{
	//通过圆类创建具体的圆，实例化
	Circle c1;
	//给圆对象的属性进行赋值操作
	c1.r = 2.2;
	cout << "圆的周长为：" << c1.zc() << endl;

	system("pause");
	return 0;
}
```

案例：

```c++;
#include<iostream>
#include<string>
using namespace std;
class Student
{
public:
	string sname;
	int sID;

	void showinfo() {
		cout << "姓名：" << sname << "学号" << sID << endl;
	}
	//给姓名赋值
	void setname(string name) {
		sname = name;
	}
	//给学号赋值
	void setID(int id) {
		sID = id;
	}
private:

};


int main()
{
	Student s1;
	s1.sname = "张三";
	s1.sID = 110;
	s1.showinfo();
	Student s2;
	s2.setname("李四");
	s2.setID(1);
	s2.showinfo();

	system("pause");
	return 0;
}
```

##### 4.1.2封装的权限控制

```c++
#include<iostream>
using namespace std;

//访问权限
//公共权限 public 类内可以访问，类外可以访问
//保护权限 protected 类内可以访问，类外不可以访问，儿子可以访问父亲中的保护内容
//私有权限 private 类内可以访问，类外不可以访问,儿子不可以访问父亲的私有内容

class person {
public:
	string pname;
	void func()//类内都可以访问
	{
		pname = "张三";
		pcar = "宝马";
		password = 123456;
	}
protected:
	string pcar;

private:
	int password;
};

int main()
{
	person p1;
	p1.pname = "李四";
	//p1.pcar = "奔驰";//改不了，会出错
	//p1.password = 111111;//改不了会出错

	system("pause");
	return 0;
}
```

##### 4.1.3struct和class的区别

struct默认权限为公共，class默认权限为私有；

##### 4.1.4将成员属性设置为私有

将成员属性设置为私有，可以自己控制读写权限；

对于写权限，我们可以控制数据的有效性；

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:
	//设置姓名
	void setName(string name) {
		pName = name;
	}
	//获取姓名
	string getName() {
		return pName;
	}
	//获取年龄
	int getAge() {
		int pAge = 10;
		return pAge;
	}

	//设置爱人
	void setLover(string lover) {
		pLover = lover;
	}
private:
	string pName;
	int pAge;
	string pLover;
};

int main() {
	Person p2;
	p2.setName("张三");
	p2.getName();

	system("pause");
	return 0;
}
```

#### 4.2对象的初始化和清理

##### 4.2.1构造函数和析构函数

构造函数语法：`类名(){}`

- 构造函数没有返回值也不写void
- 函数名称与类名相同
- 构造函数可以有参数，可以重载
- 程序在调用对象时候会自动调用构造，无需手动调用，而且指挥调用一次

析构函数语法：`~类名(){}`

- 构造函数没有返回值也不写void
- 函数名称与类名相同
- 构造函数不可以有参数
- 程序在销毁对象时候会自动调用析构函数，无需手动调用，而且指挥调用一次

```c++
#include<iostream>
using namespace std;

//构造函数 进行初始化操作
class Person
{
public:
	//构造函数，没有返回值，也不用void
	//函数名与类名相同
	//构造函数可以有参数，可以重载
	Person()
	{
		cout << "Person构造函数的调用" << endl;
	}
	//析构函数，没有返回值，也不用void
	//函数名与类名相同
	//不可以有参数，不可以重载
	//对象在销毁前自动调用析构，且只调用一次
	~Person()
	{
		cout << "person析构函数调用" << endl;
	}
};

void test01()
{
	Person p;
}

int main()
{
	test01();//会释放
	Person p1;//释放时机在关闭窗口前
	system("pause");
	return 0;
}
```

##### 4.2.2构造函数分类及调用

```c++
#include<iostream>
using namespace std;
//构造函数分类
//按照参数类型分：有参 无参
//按照函数类型分：普通 拷贝
class person
{
public:
	person()
	{
		cout << "person的无参构造函数调用" << endl;
	}
	person(int a)
	{
		age = a;
		cout << "person的有参构造函数调用" << endl;
	}
	//拷贝构造函数
	person(const person &p)//按照p完全复制一份一样的
	{
		age = p.age;
	}
	~person()
	{

	}

private:
	int age;
};

void test01()
{
	//括号法
	person p1;//调用默认构造函数不要加（）,会认为是函数声明
	person p2(10);
	person p3(p2);

	//显示法
	person p1;
	person p2 = person(10);//右侧为匿名对象
	person p3 = person(p2);
	//不要利用拷贝构造函数初始化匿名对象；
	//隐式转换法
	person p4 = 10;


	system("pause");
	return 0;
}
```

##### 4.2.3拷贝构造函数调用时机

//使用一个已经创建完毕的对象来初始化一个新对象

//值传递方式给函数参数传值

//值方式返回局部对象

```c++
#include<iostream>
using namespace std;

//拷贝构造函数调用时机

class person
{
public:
	person()
	{
		cout << "person默认构造函数调用" << endl;
	}
	person(int a)
	{
		age = a;
		cout << "person有参构造函数调用" << endl;
	}
	person(const person &p)
	{
		age = p.age;
		cout << "person拷贝构造函数调用" << endl;
	}
	~person()
	{
		cout << "析构函数调用" << endl;
	}
private:
	int age;
};
//使用一个已经创建完毕的对象来初始化一个新对象
void test01()
{
	person p1(20);
	person p2(p1);
}
//值传递方式给函数参数传值
void dowork(person p)
{

}
void test02()
{
	person p;
	dowork(p);
}
//值方式返回局部对象
person dowork2()
{
	person p1;
	return p1;
}
void test03()
{
	person p = dowork2();
}
int main()
{
	test01();

	system("pause");
	return 0;
}
```

##### 4.2.4构造函数调用规则

- 如果用户定义有参构造函数，c++不再提供默认无参构造，但是会提供拷贝构造函数
- 如果用户定义拷贝构造函数，c++不再提供构造函数

##### 4.2.5深拷贝与浅拷贝

浅拷贝：简单的赋值拷贝操作；

深拷贝：在堆区重新申请空间，进行拷贝操作；

```c++
#include<iostream>
using namespace std;

class person
{
public:
	person()
	{
		cout << "person的默认构造函数调用" << endl;
	}
	person(int a,int h)
	{
		age = a;
		height = new int(h);
		cout << "person的有参构造函数调用" << endl;
	}
	//自己实现拷贝构造函数，解决浅拷贝问题
	person(const person& p)
	{
		age = p.age;
		//height = p.height;
		//深拷贝操作
		height = new int(*p.height);
	}
	~person()
	{
		//析构代码，将堆区开辟的数据做释放操作
		if (height != NULL)
		{
			delete height;
			height = NULL;
		}
	}
	int age;
	int* height;
};

void test01()
{
	person p1(18,160);
	cout << "p1的年龄为：" << p1.age<<"身高为：" <<p1.height<< endl;
	person p2(p1);


}
```

##### 4.2.6初始化列表

语法：`构造函数():属性1(值1),属性2(值2)...{}`

```c++
#include<iostream>
using namespace std;

class person
{
public:
	//传统初始化操作
	person(int a, int b, int c)
	{
		A = a;
		B = b;
		C = c;
	}
	//初始化列表初始化属性
	person(int a,int b,int c) :A(a), B(b), C(c)
	{

	}

	int A;
	int B;
	int C;
};

void test01()
{
	person p(10, 20, 30);
	//person p;
}

int main()
{
	test01();


	system("pause");
	return 0;
}
```

##### 4.2.7类对象作为成员

c++类中的成员可以是另一个类的对象；

```c++
#include<iostream>
#include<string>
using namespace std;

class phone
{
public:
	phone(string pname)
	{
		pName = pname;
	}
	string pName;
};

class person
{
public:
	person(string name, string pname) :myname(name), myphone(pname)
	{

	}


	string myname;
	phone myphone;
};

void test01()
{
	person p("张三", "iphone");

}

int main()
{
	test01();

	system("pause");
	return 0;
}
```

##### 4.2.8静态成员

1.静态成员变量

- 所有对象共享同一份数据
- 在编译阶段分配内存
- 类内声明，类外初始化

```c++
#include<iostream>
using namespace std;

class person {
public:

	//所有对象共享同一份
	//编译阶段就分配内存
	//类内声明,类外初始化
	static int m_A;
	//静态成员变量也是有访问权限的
private:
	static int m_B;//类外不可以访问
};

int person::m_A=100;
int person::m_B = 100;
void test01()
{
	person p;
	cout << p.m_A << endl;

	person p2;
	p2.m_A = 200;//可以改变值
	cout << p2.m_A << endl;//200
}

void test02()
{
	//静态成员变量不属于某个对象，所有对象共享同一份数据
	//两种访问方式
	//通过对象进行访问
	person p3;
	cout << p3.m_A << endl;
	//通过类名进行访问
	cout << person::m_A << endl;//也能输出
}
int main()
{
	test01();

	system("pause");
	return 0;
}
```

2.静态成员函数

- 所有对象共享一个函数
- 静态成员函数只能访问静态成员变量

```c++
#include<iostream>
using namespace std;

class person
{
public:
	//静态成员函数
	static void func()
	{
		m_A = 100;//只能访问静态成员变量
		cout << "static void func 调用" << endl;
	}
	static int m_A;
};
int person::m_A = 10;
void test01()
{
	//通过对象访问
	person p;
	p.func();

	//通过类名访问
	person::func();
}

int main()
{
	test01();

	system("pause");
	return 0;
}
```

#### 4.3c++对象模型和this指针

##### 4.3.1成员变量和成员函数分开存储

在c++中，类内的成员函数和成员变量分开存储

只有非静态成员变量才在类的对象上；

##### 4.3.2this指针

this指针指向被调用的成员函数所属的对象；

this指针是隐含每一个非静态成员函数内的一种指针；

this指针不需要定义，直接使用即可；

this指针用途：

- 当形参和成员变量同名时，用this指针区分；
- 在类的非静态成员函数中返回对象本身，可使用return *this;

```c++
#include<iostream>
using namespace std;

class person
{
public:
	person(int age)
	{
		//this指针指向被调用的成员函数所属的对象
		//解决名称冲突
		this->age = age;
	}
	person &personAddAge(person& p)
	{
		this->age += p.age;
		//this指向p2的指针，而*this指向的就是p2对象的本体
		return *this;
	}
	int age;
};
void test01()
{
	person p(18);
	cout << "p的年龄为：" << p.age << endl;
}
void test02()
{
	person p1(20);
	person p2(10);
	//p2.personAddAge(p1);
	//链式编程思想
	p2.personAddAge(p1).personAddAge(p1).personAddAge(p1);
	cout << "p2的年龄为：" << p2.age << endl;
}

int main()
{
	test01();
	test02();

	system("pause");
	return 0;
}
```

4.3.3const修饰成员函数

常函数：

- 成员函数后加const后称函数为常函数
- 常函数不可以成员属性
- 成员属性声明时加关键字mutable后，在常函数中依然可以修改

常对象：

- 声明对象前const称该对象为常对象
- 常对象只能调用常函数

```c++
#include<iostream>
using namespace std;

class person
{
public:
	void showperson() const//加const后不可以修改
	{
		//m_A = 100;//加const后不可以修改
		//this->m_A = 100;//同样报错
		this->m_B = 100;
	}
	int m_A;
	mutable int m_B;//加mutable之后可以修改
};
void test01()
{

	const person p;//在对象前加常量，变成常对象
	//p.m_A = 100;//出错
	p.m_B = 100;
	//常对象只能调用常函数
	p.showperson();
}

int main()
{

	system("pause");
	return 0;
}
```

#### 4.4友元函数

友元的目的就是让一个函数或者类，访问另一个类中私有成员；

##### 4.4.1全局函数做友元

```c++
#include<iostream>
#include<string>
using namespace std;

class Building
{
	//声明为友元函数，可以访问私有成员
	friend void goodGAY(Building* building);
public:
	string m_SettingRoom;
	Building()
	{
		m_SettingRoom = "客厅";
		m_BedRoom = "卧室";
	}
private:
	string m_BedRoom;
};

//全局函数
void goodGAY(Building* building)
{
	cout << "全局函数访问" << building->m_SettingRoom << endl;
	cout << "全局函数访问" << building->m_BedRoom << endl;
}


void test01()
{
	Building b1;
	goodGAY(&b1);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.4.2类做友元

```c++
#include<iostream>
#include<string>
using namespace std;

class Building;
class GOODGay
{
public:
	GOODGay();
	void visit();//参观函数，访问building的属性
	Building* building;
};

class Building
{
	friend class GOODGay;
public:
	string m_SettingRoom;
	Building();
private:
	string m_BedRoom;
};
//类外定义构造函数
Building::Building()
{
	m_SettingRoom = "客厅";
	m_BedRoom = "卧室";
}
GOODGay::GOODGay()
{
	building = new Building;
}
void GOODGay::visit()
{
	cout << "好基友类正在访问：" << building->m_SettingRoom << endl;
}

void test01()
{
	GOODGay g1;
	g1.visit();
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.4.3成员函数做友元

```c++
#include<iostream>
using namespace std;

class person
{
public:
	//person operator +(person& p)//成员函数运算符重载
	//{
	//	person temp;
	//	temp.m_A = this->m_A + p.m_A;
	//	temp.m_B = this->m_B + p.m_B;
	//	return temp;
	//}
	int m_A;
	int m_B;
};
//全局函数重载运算符
person operator +(person &p1,person &p2)
{
	person temp;
	temp.m_A = p1.m_A + p2.m_A;
	temp.m_B = p1.m_B + p2.m_B;
	return temp;
}
void test01()
{
	person p1;
	p1.m_A = 10;
	p1.m_B = 10;

	person p2;
	p2.m_A = 10;
	p2.m_B = 10;

	person p3 = p1 + p2;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 4.5运算符重载

##### 4.5.1加号运算符重载

```c++
#include<iostream>
using namespace std;

class person
{
public:
	person operator +(person& p)//成员函数运算符重载
	{
		person temp;
		temp.m_A = this->m_A + p.m_A;
		temp.m_B = this->m_B + p.m_B;
		return temp;
	}
	int m_A;
	int m_B;
};
//全局函数重载运算符
//person operator +(person &p1,person &p2)
//{
//	person temp;
//	temp.m_A = p1.m_A + p2.m_A;
//	temp.m_B = p1.m_B + p2.m_B;
//	return temp;
//}
void test01()
{
	person p1;
	p1.m_A = 10;
	p1.m_B = 10;

	person p2;
	p2.m_A = 10;
	p2.m_B = 10;
	//成员函数重载本质调用
	person p3 = p1.operator+(p2);
	//全局函数重载本质调用
	//person p3 = operator+(p1, p2);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.5.2左移运算符重载

```c++
#include<iostream>
using namespace std;

//左移运算符重载
class person
{
public:
	//一般不会利用成员函数重载左移运算符，效果不好
	int m_A;
	int m_B;
};

//只能利用全局函数重载运算符
ostream operator<<(ostream &cout,person & p)
{
	cout << "m_A=" << p.m_A << "m_B=" << p.m_B << endl;
	return cout;
}

void test01()
{
	person p;
	p.m_A = 10;
	p.m_B = 10;

	cout << p<<endl;
}

int main()
{
	test01();

	system("pause");
	return 0;
}
```

##### 4.5.3递增运算符重载



#### 4.6继承

##### 4.6.1继承语法

```c++
//继承的基本语法
class A{}

class B:public A//B继承A的public部分
```

##### 4.6.2继承方式

公共继承

```c++
class A
{
public:
	int a;
protected:
	int b;
private:
	int c;
};

class B:protected A//B继承A的public部分
{
public:
	int a;
protected:
	int b;
//不可访问
	int c;
};
```

保护继承

```c++
class A
{
public:
	int a;
protected:
	int b;
private:
	int c;
};

class B:protected A//B继承A的protected部分
{
protected:
	int a;
	int b;
//不可访问
	int c;
};
```

私有继承

```c++
class A
{
public:
	int a;
protected:
	int b;
private:
	int c;
};

class B:private A//B继承A的private部分
{
private:
	int a;
	int b;
//不可访问
	int c;
};
```

```c++
#include<iostream>
using namespace std;

//公共继承
class Base1
{
public:
	int A;
protected:
	int B;
private:
	int C;
};
class son1 :public Base1
{
public:
	void func1()
	{
		A = 10;//父类中公共权限到子类中依然是公共权限
		B = 10;//父类中保护权限到子类中依然是保护权限
		//C=10;父类中私有权限成员 子类依然访问不到
	}
};
void test01()
{
	son1 s1;
	s1.A = 100;//公共权限类外也能访问
	//s1.B=100;保护权限类外也不能访问
}
//保护继承
class son2 :protected Base1
{
public:
	void func2()
	{
		A = 100;//父类中公共成员到子类中变为保护权限
		B = 100;//父类中保护成员不变
		//C = 100;父类中私有成员子类访问不到
	}
};
void test02()
{
	son2 s2;
	//s2.A = 100;//在子类中变成了保护权限，类外无法访问
}

class son3 :private Base1
{
public:
	void func3()
	{
		A = 100;//父类中公共成员到子类中变成私有成员
		B = 100;//父类中保护成员到子类中变成私有成员
		//C = 100;//父类中私有成员，子类访问不到
	}
};
void test03()
{
	son3 s3;
	//s3.A = 100;//变成私有成员，类外访问不到
}
```

##### 4.6.3继承中的对象模型

```c++
#include<iostream>
using namespace std;

class Base
{
public:
	int A;
protected:
	int B;
private:
	int C;
};
class son :public Base
{
public:
	int D;
};
void test01()
{
	//16B,父类中所有非静态成员都会被子类继承下去
	//父类中私有成员属性是被编译器隐藏了所以访问不到，但确实被继承下去了
	cout << "sizeof son=" << sizeof(son) << endl;
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.6.4继承中构造和析构顺序

```c++
#include<iostream>
using namespace std;

class Base
{
public:
	Base()
	{
		cout << "base构造函数" << endl;
	}
	~Base()
	{
		cout << "base析构函数" << endl;
	}
};

class Son :public Base
{
public:
	Son()
	{
		cout << "Son构造函数" << endl;
	}
	~Son()
	{
		cout << "son析构函数" << endl;
	}
};

void test()
{
	//继承中构造和析构顺序
	//先构造父类再构造子类
	//先析构子类再析构父亲
	Son s;
}
int main()
{
	test();
	system("pause");
	return 0;
}
```

##### 4.6.5继承同名成员处理方式

访问子类同名成员，直接访问即可；

访问父类同名成员，需要加作用域s.base::成员名；

```c++
#include<iostream>
using namespace std;

class Base
{
public:
	Base()
	{
		m_A = 100;
	}
	int m_A;
};
class Son :public Base
{
public:
	Son()
	{
		m_A = 200;
	}
	int m_A;
};
void test01()
{
	Son s;
	cout << "son下m_A=" << s.m_A << endl;//200
	cout << "base下m_A=" << s.Base::m_A << endl;//100
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.6.6继承同名静态成员处理方式

访问子类同名成员，直接访问即可；

访问父类同名成员，需要加作用域s.base::成员名；

##### 4.6.7多继承语法

语法：class 子类 : 继承方式 父类1，继承方式 父类2...

多继承可能会引发父类中同名成员出现，需要加作用域；

```c++
#include<iostream>
using namespace std;

class Base1
{
public:
	Base1()
	{
		A = 100;
	}
	int A;
};
class Base2
{
public:
	Base2()
	{
		A = 100;
	}
	int A;
};
class son : public Base1, public Base2
{
public:
	son()
	{
		C = 200;
		D = 300;
	}
	int C;
	int D;
};
void test01()
{
	son s;
	cout << "sizeof son=" << sizeof(son)<<endl;
	cout << "Base1 A=" << s.Base1::A << endl;
	cout << "Base2 A=" << s.Base2::A << endl;
}
int main()
{
	test01();

	system("pause");
	return 0;
}
```

##### 4.6.8菱形继承（钻石继承）

```c++
#include<iostream>
using namespace std;

class Animal
{
public:
	int Age;
};
//利用虚继承，解决菱形继承问题
//继承之前。加上关键字virtual变为虚继承
//animal类称为 虚基类
class Sheep :virtual public Animal
{

};
class Tuo :virtual public Animal
{

};
class SheepTuo :public Sheep, public Tuo
{

};
void test01()
{
	SheepTuo st;
	//两个父类拥有相同作用域需要加以区分
	st.Sheep::Age = 18;//同名成员调用时需加上从哪个类继承
	st.Tuo::Age = 28;
	//这份数据只有一份就行，菱形继承导致数据有两份，资源浪费
	
	cout << "st.Age=" << st.Age << endl;//输出结果为28
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 4.7多态

##### 4.7.1多态基本概念

静态多态和动态多态区别：

静态多态的函数地址早绑定-编译阶段确定函数地址；

动态多态的函数地址晚绑定-运行阶段确定函数地址；

```c++
#include<iostream>
using namespace std;

class Animal
{
public:
	virtual void speak()//虚函数
	{
		cout << "动物在说话" << endl;
	}
};
class Cat :public Animal
{
public:
	void speak()
	{
		cout << "小猫在说话" << endl;
	}
};

//动态多态满足条件
//1有继承关系
//2子类重写父类的虚函数
void doSpeak(Animal &aml)
{
	aml.speak();//执行的是子类 小猫在说话
}
void test01()
{
	Cat cat1;
	doSpeak(cat1);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 4.7.2多态案例1——计算器类

多态的优点：

- 可读性强
- 组织结构清晰

```c++
#include<iostream>
#include<string>
using namespace std;

//普通实现
class Caculator
{
public:
	int getResult(string oper)
	{
		if (oper == " + ")
		{
			return m_Num1 + m_Num2;
		}
		else if(oper == "-" ) {
			return m_Num1 - m_Num2;
		}
		else if (oper == "*" ) {
			return m_Num1 * m_Num2;
		}
	}
	int m_Num1;
	int m_Num2;
};
void test01()
{
	Caculator c;
	c.m_Num1 = 10;
	c.m_Num2 = 10;
}

//多态实现计算器
//实现计算器抽象类
class AbstractCaculator
{
public:
	virtual int getResult()
	{
		return 0;
	}
	int m_Num1;
	int m_Num2;
};
//加法计算器类
class AddCaculator :public AbstractCaculator
{
public:
	int getResult()
	{
		return m_Num1 + m_Num2;
	}
};
class SubCaculator :public AbstractCaculator
{
public:
	int getResult()
	{
		return m_Num1 - m_Num2;
	}
};
class MulCaculator :public AbstractCaculator
{
public:
	int getResult()
	{
		return m_Num1 * m_Num2;
	}
};
void test02()
{
	//多态使用条件
	//父类指针或引用指向子类对象
	AbstractCaculator* abc = new AddCaculator;
	abc->m_Num1 = 100;
	abc->m_Num2 = 100;
	cout << abc->getResult() << endl;
	AbstractCaculator* abc = new SubCaculator;
	abc->m_Num1 = 100;
	abc->m_Num2 = 100;
	cout << abc->getResult() << endl;
	AbstractCaculator* abc = new MulCaculator;
	abc->m_Num1 = 100;
	abc->m_Num2 = 100;
	cout << abc->getResult() << endl;
}
int main()
{
	test01();
	test02();
	system("pause");
	return 0;
}
```

##### 4.7.3纯虚函数和抽象类

纯虚函数语法：`virtual 返回值类型 函数名 （参数列表）=0`

当类中有了纯虚函数，这个类也称为抽象类；

抽象类特点：

无法实例化对象；子类必须重写抽象类中纯虚函数，否则无法实例化；

```c++
#include<iostream>
using namespace std;

class Base
{
public:
	//无法实例化对象
	virtual void func() = 0;
};
class Son :public Base
{
public:
	virtual void func() {};
};
```

##### 4.7.4虚析构和纯虚析构

虚析构和纯虚析构只需要写一个就行；

```c++
//虚析构
virtual ~类名(){}

//纯虚析构
virtual ~类名()=0;
类名::~类名(){}
```

```c++
#include<iostream>
#include<string>
using namespace std;

class Animal
{
public:
	virtual void speak() = 0;
	Animal() 
	{

	};
	////虚析构可以解决 父类指针释放子类对象时不干净的问题
	//virtual ~Animal()
	//{
	//	cout << "animal虚析构函数调用" << endl;
	//}
	//纯虚析构，需要声明也需要实现
    //有纯虚析构也属于抽象类，无法实例化对象
	virtual ~Animal() = 0;
};
//纯虚析构实现
Animal::~Animal()
{
	cout << "animal纯虚析构函数调用" << endl;
}
class Cat :public Animal
{
public:
	Cat(string name)
	{
		m_Name = new string(name);
	}
	virtual void speak()
	{
		cout << "小猫在说话" << endl;
	}
	string* m_Name;
	~Cat()
	{
		if (m_Name != NULL)
		{
			cout << "cat析构函数调用" << endl;
		}
	}
};
void test01()
{
	Animal * animal = new Cat("tom");
	animal->speak();
	delete animal;
}

```

### 5文件操作

程序运行时产生的数据都属于临时数据，程序一旦运行结束都会被释放；通过文件可以将数据持久化；

c++中对文件操作需要包含头文件`<fstream>`;

文本文件：文件以文本的ASCII码形式存储在计算机中；

二进制文件：文件以文本的二进制形式存储在计算机中；

操作文件三大类：

ofstream：写操作；

ifstream:读操作；

fstream：读写操作；

#### 5.1文本文件

##### 5.1.1写文件

写文件步骤如下：

1. 包含头文件`#include<fstream>`
2. 创建流对象`ofstream ofs`
3. 打开文件 `ofs.open{"文件路径",打开方式}`
4. 写数据 ofs<<"写入的数据";
5. 关闭文件 ofs.close();

文件打开方式：

| ios::binary | 二进制方式                 |
| ----------- | -------------------------- |
| ios::in     | 为读文件而打开文件         |
| ios::out    | 为写文件而打开文件         |
| ios::ate    | 初始位置：文件尾           |
| ios::app    | 追加方式写文件             |
| ios::trunc  | 如果文件存在先删除，再创建 |

注意：文件打开方式可以配合使用，利用|操作符；

例如：用二进制方式写文件`ios::binary|ios::out`

```c++
#include<iostream>
#include<fstream>
using namespace std;
void test01()
{
	//创建流对象
	ofstream ofs;
	//指定打开方式
	ofs.open("test.txt", ios::out);
	//写内容
	ofs << "姓名：张三" << endl;
	ofs << "性别：男" << endl;
	//关闭文件
	ofs.close();
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 5.1.2读文件

写文件步骤如下：

1. 包含头文件`#include<fstream>`
2. 创建流对象`ifstream ifs`
3. 打开文件 `ifs.open{"文件路径",打开方式}`
4. 读数据  四种方式读取；
5. 关闭文件 ifs.close();

```c++
#include<iostream>
#include<fstream>
#include<string>
using namespace std;

void test02()
{
	//创建流对象
	ifstream ifs;
	//打开文件并判断是否打开成功
	ifs.open("test.txt", ios::in);
	if (!ifs.is_open())
	{
		cout << "文件打开失败" << endl;
		return;
	}
	//读数据
	//第一种读取
	/*char buf[1024] = { 0 };
	while (ifs >> buf)
	{
		cout << buf << endl;
	}*/
	//第二种读取
	/*char buf[1024] = { 0 };
	while (ifs.getline(buf, sizeof(buf)))
	{
		cout << buf << endl;
	}*/
	//第三种
	/*string buf;
	while (getline(ifs,buf))
	{
		cout << buf << endl;
	}*/
	//第四种不推荐
	char c;
	while ((c = ifs.get() )!= EOF)
	{
		cout << c;
	}
	//关闭文件
	ifs.close();
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 5.2二进制文件

##### 5.2.1写文件

函数原型：`ostream& write(const char * buffer,int len);`

```c++
#include<iostream>
#include<fstream>
using namespace std;

class Person
{
public:
	char m_Name[64];//姓名
	int m_Age;//年龄
};

void test03()
{
	//创建流对象
	ofstream ofs1;
	//打开文件
	ofs1.open("person.txt", ios::out | ios::binary);
	//写文件
	Person p = { "张三",18 };
	ofs1.write((const char*)&p, sizeof(Person));
	//关闭文件
	ofs1.close();
}
int main()
{
	test03();
	system("pause");
	return 0;
}
```

##### 5.2.2读文件

函数原型：`istream& read(char *buffer,int len);`

```c++
#include<iostream>
#include<fstream>
using namespace std;

class person
{
public:
	char m_Name[64];//姓名
	int m_Age;//年龄
};

void test04()
{
	ifstream ifs1;
	ifs1.open("person.txt",ios::in|ios::binary);
	if (!ifs1.is_open())
	{
		cout << "文件打开失败" << endl;
	}
	person p;
	ifs1.read((char*)&p, sizeof(person));
	cout << "姓名：" << p.m_Name << "年龄：" << p.m_Age << endl;
	ifs1.close();
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

## c++提高

本阶段主要针对c++泛型编程和STL技术做详细讲解；

### 1.模板

#### 1.1模板概念

通用的模具，提高复用性；

#### 1.2函数模板

##### 1.2.1模板语法

建立一个通用函数，返回值类型和形参类型可以不具体设定，用虚拟类型代表

语法：`template<typename T>`

template--声明创建模板

```c++
#include<iostream>
using namespace std;

//函数模板
template<typename T>//声明一个模板
void myswap(T& a, T& b)
{
	T temp = a;
	a = b;
	b = temp;
}

void test01()
{
	int a = 10;
	int b = 20;
	//两张方式使用函数模板
	myswap(a, b);//自动类型推导
	myswap<int>(a, b);//声明数据类型
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 1.2.2函数模板注意事项

自动类型推导：必须推导出一致的数据类型T才能使用；

模板必须要确定出T的数据类型，才可以使用；

```c++
#include<iostream>
using namespace std;
//自动类型推导,必须推导出一致的数据类型
template<typename T>
void mySwap(T& a, T& b)
{
	T temp = a;
	a = b;
	b = temp;
}
void test02()
{
	int a = 10;
	int b = 20;
	char c = 'c';
	//两张方式使用函数模板
	//mySwap(a, c);//自动类型推导类型不一致，错误
}
//模板必须确定T的数据类型，才可以使用
template<class T>
void func()
{
	cout << "func调用" << endl;
}
void test03()
{
	//func();//出错，没有指定T的类型
	func<int>();//随便给一个数据类型就行
}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

##### 1.2.3函数模板案例--数组排序

```c++
#include<iostream>
using namespace std;

template<typename T>
void MySwap(T& a, T& b)
{
	T temp = a;
	a = b;
	b = temp;
}
//排序算法
template<typename T>
void mySort(T arr[],int len)
{
	for (int i = 0; i < len; i++)
	{
		int max = i;
		for (int j = i + 1; j < len; j++)
		{
			if (arr[max] < arr[j])
			{
				max = j;
			}
		}
		if (max != i)
		{
			MySwap(arr[max], arr[i]);
		}
	}
}
template<class T>
void printArr(T arr[],int len)
{
	for (int i = 0; i < len; i++)
	{
		cout << arr[i] << " ";
	}
}
void test04()
{
	char charArr[] = "badcfe";
	int num = sizeof(charArr)/sizeof(char);
	mySort(charArr, num);
	printArr(charArr, num);
}
void test05()
{
	int arr[] = { 3,4,2,6,5,8,7,9 };
	int num = sizeof(arr) / sizeof(int);
	mySort(arr, num);
	printArr(arr, num);
}
int main()
{
	test04();
	test05();
	system("pause");
	return 0;
}
```

##### 1.2.4普通函数与函数模板的区别

- 普通函数可以发生隐式类型转换；
- 函数模板自动类型推导时不可以进行隐式类型转换；
- 函数模板显示指定类型可以发生隐式类型转换；

```c++
#include<iostream>
using namespace std;
int myAdd01(int a ,int b)
{
	return a + b;
}
template<class T>
T myAdd02(T a,T b)
{
	return a + b;
}
void test06()
{
	int a = 10;
	int b = 20;
	char c = 'c';
	//普通可以计算，将字符型转成了整型 c=99
	cout << myAdd01(a, c) << endl;
	//自动推导类型报错，不是同类数据
	//cout << myAdd02(a, c) << endl;
	//显示指定类型调用函数模板,可以进行隐式转换计算
	cout << myAdd02<int>(a, c) << endl;
}
int main()
{
	test06();
	system("pause");
	return 0;
}
```

##### 1.2.5普通函数和函数模板的调用规则

1. 普通函数和函数模板都可以实现，优先调用普通函数

```c++
void myPrint(int a, int b)
{
	cout << "调用普通函数" << endl;
}
template<class T>
void myPrint(T a, T b)
{
	cout << "调用函数模板" << endl;
}
void test07()
{
	int a = 1;
	int b = 2;
	myPrint(a, b);//调用普通函数
}
```

2.可以通过空模板参数列表来强制调用函数模板

```c++
void myPrint(int a, int b)
{
	cout << "调用普通函数" << endl;
}
template<class T>
void myPrint(T a, T b)
{
	cout << "调用函数模板" << endl;
}
void test07()
{
	int a = 1;
	int b = 2;
	//myPrint(a, b);默认调用普通函数
	//通过空模板参数列表强制调用函数模板
	myPrint<>(a, b);//调用函数模板
}
```

3.函数模板也可以发生重载

```c++
template<class T>
void myPrint(T a, T b)
{
	cout << "调用函数模板" << endl;
}
template<class T>
void myPrint(T a, T b,T c)
{
	cout << "调用重载函数模板" << endl;
}
```

4.如果函数模板可以更好的匹配，优先调用函数模板

```c++

void myPrint(int a, int b)
{
	cout << "调用普通函数" << endl;
}
template<class T>
void myPrint(T a, T b)
{
	cout << "调用函数模板" << endl;
}
void test07()
{
	char a = 'a';
	char b = 'b';
	myPrint(a, b);//调用函数模板
}
```

##### 1.2.6模板的局限性

模板的通用性并不是万能的；

#### 1.3类模板

##### 1.3.1类模板语法

建立一个通用类，类中成员数据类型可以不具体指定，用虚拟类型代表；

```c++
#include<iostream>
#include<string>
using namespace std;

//类模板
template<class NameType,class AgeType>
class Person
{
public:
	Person(NameType name,AgeType age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}
	void showPerson()
	{
		cout << "name:" << this->m_Name << endl;
		cout << "age:" << this->m_Age << endl;
	}
	NameType m_Name;
	AgeType m_Age;
};
void test01()
{
	Person<string, int>p1("孙悟空", 999);
	p1.showPerson();
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 1.3.2类模板与函数模板的区别

- 类模板没有自动类型推导的使用方式
- 类模板在模板参数列表里可以有默认参数

```c++
#include<iostream>
using namespace std;

template<class NameType, class AgeType = int >
class Person
{
public:
	Person(NameType name, AgeType age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}
	void showPerson()
	{
		cout << "name:" << this->m_Name << endl;
		cout << "age:" << this->m_Age << endl;
	}
	NameType m_Name;
	AgeType m_Age;
};


//类模板没有自动类型推导的使用方式
void test02()
{
	//Person p("孙悟空", 999);//出错需要指定数据类型
	Person<string, int>p("孙悟空", 999);
	p.showPerson();
}

void test03()
{
	//模板参数列表中可以有默认参数
	Person<string>p("猪八戒", 999);
}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

##### 1.3.3类模板中成员函数创建时机

- 普通类中成员函数一开始就可以创建
- 类模板中成员函数在调用时才创建

```c++
#include<iostream>
using namespace std;

//类模板成员函数创建时机,调用时创建
class Person1
{
public:
	void showPerson1()
	{
		cout << "person1 show" << endl;
	}
};

class Person2
{
public:
	void showPerson1()
	{
		cout << "person1 show" << endl;
	}
};

template<class T>
class myClass
{
public:
	T obj;
	void func1()
	{
		obj.showPerson1();
	}
	void func2()
	{
		obj.showPerson2();
	}
};
void test04()
{
	myClass<Person1> m1;
	m1.func1();
	myClass<Person2> m2;
	m2.func2();
}
int main()
{
	test04();
	system("pause");
	return 0;
}
```

##### 1.3.4类模板对象做函数参数

类模板实例化出的对象，向函数传参的方式；

三种传入方式：

1. 指定传入方式--直接显示对象的数据类型,使用较多
2. 参数模板化    --将对象中的参数变为模板进行传递
3. 整个类模板化--将这个对象模型模板化进行传递

```c++
#include<iostream>
#include<string>
using namespace std;

template<class T1,class T2>
class Person
{
public:
	Person(T1 name, T2 age)
	{
		this->m_age = age;
		this->m_name = name;
	}
	void showPerson()
	{
		cout << this->m_age << this->m_name << endl;
	}
	T1 m_name;
	T2 m_age;
};
//指定传入类型
void printPerson1(Person<string, int>&p)
{
	p.showPerson();
}
void test05()
{
	Person<string, int>p("孙悟空", 99);
	printPerson1(p);
}
//参数模板化
template<class T1,class T2>
void printPerson2(Person<T1,T2>& p)
{
	p.showPerson();
}
void test06()
{
	Person<string, int>p("猪八戒", 89);
	printPerson2(p);
}
//整个类模板化
template<class T>
void printPerson3(T &p)
{
	p.showPerson();
}
void test07()
{
	Person<string, int>p("唐僧", 80);
	printPerson3(p);
}
int main()
{
	test05();
	test06();
	test07();
	system("pause");
	return 0;
}

```

##### 1.3.5类模板与继承

- 当子类继承的父类是一个类模板时，子类在声明的时候，需要指明父类中T的类型；
- 如果不指定，编译器无法给子类分配内存；
- 如果想灵活指定出父类中T的类型，子类也需要变成类模板；

```c++
#include<iostream> 
using namespace std;

template<class T>
class Base
{
	T m;
};

//class Son :public Base//必须知道父类的T类型，才能继承给子类
class Son : public Base<int>
{

};
void test07()
{
	Son s1;
}
//如果想灵活指定父类中T类型，子类也需要变类模板
template<class T1,class T2>
class Son2 :public Base<T2>
{
	T1 obj;
};
void test08()
{
	Son2<int, char>s2;
}
int main()
{

	system("pause");
	return 0;
}
```

##### 1.3.6类模板成员函数类外实现

```c++
#include<iostream>
#include<string>
using namespace std;

template<class T1,class T2>
class Person
{
public:
	Person(T1 name, T2 age);
	void showPerson();
	T1 m_name;
	T2 m_age;
};
//构造函数类外实现
template<class T1,class T2>
Person<T1,T2>::Person(T1 name, T2 age)
{
	this->m_age = age;
	this->m_name = name;
}
//成员函数类外实现
template<class T1, class T2>
void Person<T1,T2>::showPerson()
{
	cout << this->m_age << this->m_name << endl;
}
int main()
{

	system("pause");
	return 0;
}
```

##### 1.3.7类模板分文件编写

问题：类模板中成员函数创建时机是在调用阶段，导致分文件编写时链接不到

解决：方法1：直接包含.cpp源文件

person.h

```c++
#pragma once
#include<iostream>
#include<string>
using namespace std;

template<class T1, class T2>
class Person
{
public:
	Person(T1 name, T2 age);
	void showPerson();
	T1 m_name;
	T2 m_age;
};
```

person.cpp

```c++
#include"person.h"

//构造函数类外实现
template<class T1, class T2>
Person<T1, T2>::Person(T1 name, T2 age)
{
	this->m_age = age;
	this->m_name = name;
}
//成员函数类外实现
template<class T1, class T2>
void Person<T1, T2>::showPerson()
{
	cout << this->m_age << this->m_name << endl;
}
```

```c++
#include<iostream>
#include<string>
using namespace std;
#include"person.cpp"
//template<class T1,class T2>
//class Person
//{
//public:
//	Person(T1 name, T2 age);
//	void showPerson();
//	T1 m_name;
//	T2 m_age;
//};
////构造函数类外实现
//template<class T1, class T2>
//Person<T1, T2>::Person(T1 name, T2 age)
//{
//	this->m_age = age;
//	this->m_name = name;
//}
////成员函数类外实现
//template<class T1, class T2>
//void Person<T1, T2>::showPerson()
//{
//	cout << this->m_age << this->m_name << endl;
//}
void test10()
{
	Person <string, int>p("tom", 19);
	p.showPerson();
}
int main()
{
	test10();
	system("pause");
	return 0;
}
```

方法2：将声明和实现写到同一文件中，并更改后缀名为.hpp(主流方法)

person.hpp

```c++
#pragma once
#include<iostream>
#include<string>
using namespace std;

template<class T1, class T2>
class Person
{
public:
	Person(T1 name, T2 age);
	void showPerson();
	T1 m_name;
	T2 m_age;
};

//构造函数类外实现
template<class T1, class T2>
Person<T1, T2>::Person(T1 name, T2 age)
{
	this->m_age = age;
	this->m_name = name;
}
//成员函数类外实现
template<class T1, class T2>
void Person<T1, T2>::showPerson()
{
	cout << this->m_age << this->m_name << endl;
}
```

```c++
#include<iostream>
#include<string>
using namespace std;
#include"person.hpp"

void test10()
{
	Person <string, int>p("tom", 19);
	p.showPerson();
}
int main()
{
	test10();
	system("pause");
	return 0;
}
```

##### 1.3.8类模板与友元

全局函数类内实现--直接在类内声明友元即可；

全局函数类外实现--直接提前让编译器知道全局函数的存在；(太复杂)

```c++
#include<iostream>
#include<string>
using namespace std;

template<class T1, class T2>
class Person;
//全局函数类外实现
template<class T1, class T2>
void printPerson2(Person<T1, T2> p)
{
	cout << p.m_age << p.m_name;
}
template<class T1, class T2>
class Person
{
	//全局函数类内实现
	/*friend void printPerson(Person<T1, T2> p)；
	{
		cout << p.m_age << p.m_name;
	}*/
	//全局函数类外实现声明，要加一个空模板参数列表
	friend void printPerson2<>(Person<T1, T2> p);
public:
	Person(T1 name, T2 age)
	{
		this->m_age = age;
		this->m_name = name;
	}
private:
	T1 m_name;
	T2 m_age;
};
void test11()
{
	Person<string, int>p("tom", 20);
	printPerson2(p);
}
int main()
{
	test11();
	system("pause");
	return 0;
}
```

### 2.STL初识

#### 2.1STL基本概念

- STL(standard template libary)标准模板库
- STL广义上分为：容器(container)算法(algorithm)迭代器(iterator)
- 容器和算法之间通过迭代器无缝连接
- STL几乎所有代码都采用了模板类或者模板函数

#### 2.2STL六大组件

1. 容器：各种数据结构，如vector、list、deque、set、map等
2. 算法：各种常用算法，如sort、find、copy、for_each等
3. 迭代器：容器和算法的胶合剂
4. 仿函数：行为类似函数，可作为算法的某种策略
5. 适配器：用来修饰容器或仿函数或迭代器接口的东西
6. 空间配置器：负责空间的配置与管理

#### 2.3STL中容器、算法、迭代器

**容器：**

序列式容器：强调值的顺序，序列式容器中每个元素均有固定的位置；

关联式容器：二叉树结构，个元素之间没有严格的物理上的顺序关系；

**算法：**

质变算法：指运算过程中会更改区间内的元素的内容，例如拷贝、替换、删除等；

非质变算法：指运算过程中不会更改区间内的元素的内容，例如查找、计数、遍历、寻找极值等；

**迭代器：**容器和算法的胶合剂；

#### 2.4容器算法迭代器初识

##### 2.4.1vector存放内置数据类型

容器：`vector`

算法：`for_each`

迭代器：`vector<int>::iterator`

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>
//vector容器存放内置数据类型
void myPrint(int val)
{
	cout << val << endl;
}
void test01()
{
	//创建一个vector容器，数组
	vector<int> v;
	//向容器中插入数据
	v.push_back(10);
	v.push_back(20);
	v.push_back(30);
	v.push_back(40);

	//通过迭代器访问容器中的数据
	//vector<int>::iterator itBegin = v.begin();//起始迭代器，指向容器中第一个元素
	//vector<int>::iterator itEnd = v.end();//末尾迭代器，指向数组中最后一个迭代器下一个位置

	////第一种遍历方式
	//while (itBegin != itEnd)
	//{
	//	cout << *itBegin << endl;
	//	itBegin++;
	//}

	//第二种遍历方式
	//for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	//{
	//	cout << *it << endl;
	//}

	//第三种遍历方式，利用STL提供的遍历算法
	for_each (v.begin(), v.end(), myPrint);
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 2.4.2vector存放自定义数据类型

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<string>
class Person
{
public:
	Person(string name, int age)
	{
		this->m_age = age;
		this->m_name = name;
	}
	string m_name;
	int m_age;
};

void test02()
{
	vector<Person> v;
	Person p1("a", 10);
	Person p2("b", 20);
	Person p3("c", 30);
	Person p4("d", 40);
	Person p5("e", 50);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);
	v.push_back(p5);

	for (vector<Person>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << "姓名：" << (*it).m_name 
			<< "年龄:" << (*it).m_age << endl;
	}
}
 //存放自定义数据类型  指针
void test03()
{
	vector<Person*> v;
	Person p1("a", 10);
	Person p2("b", 20);
	Person p3("c", 30);
	Person p4("d", 40);
	Person p5("e", 50);
	v.push_back(&p1);
	v.push_back(&p2);
	v.push_back(&p3);
	v.push_back(&p4);
	v.push_back(&p5);
	for (vector<Person*>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << "姓名:" << (*it)->m_name << "年龄：" << (*it)->m_age << endl;
	}
}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

##### 2.4.3vector容器嵌套容器

```c++
#include<iostream>
#include<vector>
using namespace std;

void test04()
{
	vector<vector<int >> v;

	vector<int> v1;
	vector<int> v2;
	vector<int> v3;
	vector<int> v4;
	//小容器中插入数据
	for (int i = 0; i < 4; i++)
	{
		v1.push_back(i + 1);
		v2.push_back(i + 2);
		v3.push_back(i + 3);
		v4.push_back(i + 4);
	}
	//将小容器插入大容器
	v.push_back(v1);
	v.push_back(v2);
	v.push_back(v3);
	v.push_back(v4);
	//通过大容器把所有数据遍历一般
	for (vector<vector<int>>::iterator it = v.begin(); it != v.end(); it++)
	{
		for (vector<int>::iterator vit = (*it).begin(); vit != (*it).end(); vit++)
		{
			cout << *vit << " ";
		}
		cout << endl;
	}
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

### 3.STL--string容器

#### 3.1string基本概念

string和char*的区别：

- char *是一个指针；
- `string是一个类，类内部封装了char*，管理这个字符串，是一个char*型的容器`

构造函数：

- `string()`  创建一个空的字符串
- `string(const char* s)` 使用字符串初始化
- `string(const string& str)` 使用一个string对象初始化另一个string对象
- `string(int n,char c)` 使用n个字符c初始化

```c++
#include<iostream>

#include<string>
using namespace std;

void test01()
{
	string s1;//默认构造

	const char* str = "hello world";
	string s2(str);

	cout << "s2=" << s2 << endl;
	string s3(s2);
	cout << "s3=" << s3 << endl;

	string s4(10, 'a');
	cout << "s4=" << s4 << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 3.2赋值操作

赋值的函数原型：

```c++
string& operator=(const char* s);//char*类型字符串 赋值给当前的字符串
string& operator=(const string& s);//把字符串s赋值给当前字符串
string& operator=(char c);//字符赋值给当前字符串
string& assign(const char *s);//把字符串s赋值给当前字符串
string& assign(const char* s, int n);//把字符串s的前n个字符赋给当前字符串
string& assign(const string& s);//把字符串s赋给当前字符串
string& assign(int n, char c);//用n个字符c赋值给当前字符串
```

```c++
#include<iostream>
#include<string>
using namespace std;

//string赋值操作

//string& operator=(const char* s);//char*类型字符串 赋值给当前的字符串
//string& operator=(const string& s);//把字符串s赋值给当前字符串
//string& operator=(char c);//字符赋值给当前字符串
//string& assign(const char *s);//把字符串s赋值给当前字符串
//string& assign(const char* s, int n);//把字符串s的前n个字符赋给当前字符串
//string& assign(const string& s);//把字符串s赋给当前字符串
//string& assign(int n, char c);//用n个字符c赋值给当前字符串

void test02()
{
	string str1;
	str1 = "hello world";
	cout << "str1=" << str1 << endl;

	string str2;
	str2 = str1;
	cout << "str2=" << str2 << endl;

	string str3;
	str3 = 'a';
	cout << "str3=" << str3 << endl;

	string str4;
	str4.assign("hello c++");
	cout << "str4=" << str4 << endl;

	string str5;
	str5.assign("hello c++", 5);
	cout << "str5=" << str5 << endl;

	string str6;
	str6.assign(str5);
	cout << "str6=" << str6 << endl;

	string str7;
	str7.assign(10, 'a');
	cout << "str7=" << str7 << endl;
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 3.3string字符串拼接

函数原型：

```c++
//string& operator+=(const char* str);//重载+=操作符
//string& operator+=(const char c);//重载+=操作符
//string& operator+=(const string& str);//重载+=操作符
//string& append(const char* s);//把字符串s连接到当前字符串结尾
//string& append(const char* s，int n);//把字符串s的前n个字符连接到当前字符串结尾
//string& append(const string &s);//把字符串s赋值给当前字符串
//string& append(const string &s,int pos,int n);//把字符串s中从pos开始的n个字符连接到当前字符串结尾
```

```c++
#include<iostream>
#include<string>
using namespace std;

//string& operator+=(const char* str);//重载+=操作符
//string& operator+=(const char c);//重载+=操作符
//string& operator+=(const string& str);//重载+=操作符
//string& append(const char* s);//把字符串s连接到当前字符串结尾
//string& append(const char* s，int n);//把字符串s的前n个字符连接到当前字符串结尾
//string& append(const string &s);//把字符串s赋值给当前字符串
//string& append(const string &s,int pos,int n);//把字符串s中从pos开始的n个字符连接到当前字符串结尾

void test03()
{
	string str1="我";
	str1 += "爱玩游戏";
	cout << "str1=" << str1 << endl;

	str1 += ':';
	cout << "str1=" << str1 << endl;
	
	string str2 = "LOL DNF";

	str1 += str2;
	cout << "str1=" << str1 << endl;

	string str3 = "I";
	str3.append("love");
	cout << "str3=" << str3 << endl;

	str3.append("game abcde", 4);
	cout << "str3=" << str3 << endl;

	str3.append(str2);
	cout << "str3=" << str3 << endl;

	str3.append(str2, 4, 3);
	cout << "str3=" << str3 << endl;

}

int main()
{
	test03();
	system("pause");
	return 0;
}
```

#### 3.4string查找和替换

- find查找是从左往右，rfind是从右往左
- find找到字符串后返回查找到的第一个字符位置，找不到返回-1
- replace替换时，要指定从哪个位置起，多少个字符，替换成什么样的字符串

```c++
#include<iostream>
#include<string>
using namespace std;
//查找
void test04()
{
	string str1 = "abcdefg";
	//从左往右查。返回位置，0开始排序，没找到返回-1
	int position= str1.find("de");
	if (position == -1)
	{
		cout << "未找到字符串" << endl;
	}
	else
	{
		cout << "pos=" << position << endl;
	}
	//rfind从右往左查
	int pos = str1.rfind("de");
	
}

//替换
void test05()
{
	string str2 = "abcdefg";
	str2.replace(1, 3, "1111");//从1号位置起三个字符替换为1111

}
```

#### 3.5string字符串比较

字符串比较是按字符的ASCII码进行对比

=返回0，>返回1，<返回-1；

```c++
#include<iostream>

using namespace std;

void test06()
{
	string str1 = "hello";
	string str2 = "hello";

	if (str1.compare(str2) == 0)
	{
		cout << "str1等于str2" << endl;
	}
	else if (str1.compare(str2) > 0) {
		cout << "str1大于str2" << endl;
	}
	else {
		cout << "str1小于str2" << endl;
	}
}

int main()
{
	test06();
	system("pause");
	return 0;
}
```

#### 3.6string字符存取

string中单个字符存取方式有两种：

- `char& operator[](int n);`//通过[]方式存取字符
- `char& at(int n);` //通过at方法获取字符

```c++
//string字符存取
void test07()
{
	string str = "hello";

	//通过[]访问单个字符
	for (int i = 0; i < str.size(); i++)
	{
		cout << str[i] << " ";
	}
	cout << endl;

	//通过at方式访问单个字符
	for (int i = 0; i < str.size(); i++)
	{
		cout << str.at(i) << " ";
	}
	cout << endl;

	//修改单个字符
	str[0] = 'x';
	str.at(1) = 'x';
}
```

#### 3.7string插入和删除

```c++
//字符串插入和删除
void test()
{
	string str = "hello";

	//插入
	str.insert(1, "111");

	//删除
	str.erase(1, 3);
}
```

#### 3.8string子串获取

从字符串中获取想要的子串；

`string substr(int pos=0,int n = npos) const`

```c++
//string求子串

void test()
{
	string str = "abcdef";
	//从1号位置截取3个字符
	string subStr = str.substr(1, 3);
}
```

### 4.STL--vector容器

####  4.1vector基本概念

- vector数据结构与数组相似，也称为==单端数组；（尾部插入）==
- vector和普通数组的区别：**==数组是静态空间，而vector可以动态扩展==**；
- 动态扩展：并==不是在原空间后接续新空间==，而是==找更大的内存空间，然后将元数据拷贝到新空间，释放原空间；==

#### 4.2vector构造函数

```c++
#include<iostream>
#include<vector>
using namespace std;

void printVector(vector<int>& v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

void test01()
{
	vector<int> v1;//默认无参构造
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	printVector(v1);

	//通过区间方式构造
	vector<int> v2(v1.begin()+2, v1.end()-2);
	printVector(v2);

	//n个elme方式构造
	vector<int> v3(10, 100);//10个100
	printVector(v3);

	//拷贝构造
	vector<int> v4(v3);
	printVector(v4);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 4.3赋值操作

```c++
#include<iostream>
#include<vector>
using namespace std;

void printVector2(vector<int>& v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

//vector赋值
void test02()
{
	vector<int> v1;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	printVector2(v1);

	//赋值 operator=
	vector<int> v2;
	v2 = v1;
	printVector2(v2);

	//assign
	vector<int>v3;
	v3.assign(v1.begin()+1, v1.end()-2);
	printVector2(v3);

	//n个elem方式赋值
	vector<int> v4;
	v4.assign(10, 1);//10个1
	printVector2(v4);
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 4.4vector容量和大小

```c++
#include<iostream>
#include<vector>
using namespace std;


void printVector3(vector<int>& v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

void test03()
{
	vector<int> v1;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	printVector3(v1);
	//判断容器是否为空
	if (v1.empty())//为真代表容器为空
	{
		cout << "v1为空" << endl;
	}
	else {
		cout << "v1不为空" << endl;
		cout << "v1的容量为：" << v1.capacity() << endl;
		cout << "v1的大小为：" << v1.size() << endl;
	}

	//重新指定大小
	v1.resize(15,100);//扩大之后默认用0填充，可以利用参数指定默认填充值
	printVector3(v1);
	v1.resize(5);//缩短之后，超出部分删除
	printVector3(v1);
}

int main()
{
	test03();
	system("pause");
	return 0;
}
```

#### 4.5vector容器插入和删除

```c++
#include<iostream>
#include<vector>
using namespace std;
void printVector4(vector<int>& v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test04()
{
	vector<int> v1;
	//尾插
	v1.push_back(10);
	v1.push_back(20);
	v1.push_back(30);
	v1.push_back(40);
	v1.push_back(50);

	//遍历
	printVector4(v1);

	//尾删
	v1.pop_back();
	printVector4(v1);

	//插入
	v1.insert(v1.begin(), 100);
	printVector4(v1);

	v1.insert(v1.begin(), 2, 1000);//在迭代器位置插入2个1000
	printVector4(v1);
	//删除
	v1.erase(v1.begin());
	printVector4(v1);
	//v1.erase(v1.begin(), v1.end());//从头到尾删除
	v1.clear();//清空操作
	printVector4(v1);
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 4.6vector数据存取

```c++
#include<iostream>
#include<vector>
using namespace std;

void test05()
{
	vector<int> v1;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	//利用[]方式访问数组中元素
	for (int i = 0; i < v1.size(); i++)
	{
		cout << v1[i] << " ";
	}
	cout << endl;
	//利用at方式访问元素
	for (int i = 0; i < v1.size(); i++)
	{
		cout << v1.at(i) << " ";
	}
	cout << endl;
	//获取第一个元素
	cout << "第一个元素为：" << v1.front() << endl;

	//获取最后一个元素
	cout << "最后一个元素为：" << v1.back() << endl;

}
int main()
{
	test05();
	system("pause");
	return 0;
}
```

#### 4.7vector互换容器

实现两个容器内元素互换；

```c++
#include<iostream>
#include<vector>
using namespace std;

void printVector6(vector<int>& v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test06()
{
	vector<int> v1;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	cout << "互换前打印" << endl;

	printVector6(v1);

	vector<int>v2;
	for (int i = 10; i >0; i--)
	{
		v2.push_back(i);
	}
	printVector6(v2);

	v1.swap(v2);//v1与v2交换内容
	cout << "互换后打印" << endl;
	printVector6(v1);
	printVector6(v2);
}

//实际用途
//巧用swap可以收缩内存空间
void test07()
{
	vector<int>v;
	for (int i = 0; i < 100000; i++)
	{
		v.push_back(i);
	}
	cout << "v的容量为：" << v.capacity() << endl;
	cout << "v的大小为：" << v.size() << endl;

	v.resize(3);//重新指定大小
	//重新指定大小后容量是不变的，只是缩短了实际大小
	cout << "v的容量为：" << v.capacity() << endl;
	cout << "v的大小为：" << v.size() << endl;
	//巧用swap收缩内存
	vector<int>(v).swap(v);
	cout << "v的容量为：" << v.capacity() << endl;
	cout << "v的大小为：" << v.size() << endl;
}

int main()
{
	test06();
	test07();
	system("pause");
	return 0;
}
```

#### 4.8vector预留空间

减少vector在动态扩展容量时的扩展次数；

reserve(int len);//容器中预留len个空间

```c++
#include<iostream>
#include<vector>
using namespace std;
void test08()
{
	vector<int>v;
	//利用reserve预留空间，就不用不断开辟新空间
	v.reserve(100000);
	int num = 0;//统计开辟新空间次数
	int* p = NULL;
	for (int i = 0; i < 100000; i++)
	{
		v.push_back(i);
		if (p != &v[0])
		{
			p = &v[0];
			num++;
		}
	}
	cout << num << endl;
}
int main()
{
	test08();
	system("pause");
	return 0;
}
```

### 5.STL--deque容器

#### 5.1deque容器基本概念

功能：==双端数组==，可以对头端进行插入删除操作；

deque和vector的区别：

- vector对于头部的插入删除效率低，数据量越大，效率越低；
- deque相对而言，对头部的插入速度会比vector快
- vector访问元素时的速度会比deque快，这和两者内部实现有关

deque内部工作原理：

deque内部有个中控器，维护每段缓冲区中的内容，缓冲区中存放真实数据；

中控器维护的是每个缓冲区的地址，使得使用deque时像一片连续的内存空间；

deque容器的迭代器也是支持随机访问的；

#### 5.2deque构造函数

```c++
#include<iostream>
#include<deque>
using namespace std;

void printDeque(const deque<int>& d)
{
	for (deque<int>::const_iterator it = d.begin(); it != d.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

void test01()
{
	deque<int>d1;
	for (int i = 0; i < 10; i++)
	{
		d1.push_back(i);
	}
	printDeque(d1);

	deque<int>d2(d1.begin(), d1.end());
	printDeque(d2);

	deque<int>d3(10, 100);//10个100
	printDeque(d3);

	deque<int>d4(d3);
	printDeque(d4);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 5.3deque赋值操作

```c++
#include<iostream>
#include<deque>
using namespace std;

void printDeque2(const deque<int>& d)
{
	for (deque<int>::const_iterator it = d.begin(); it != d.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

void test02()
{
	deque<int> d1;
	for (int i = 0; i < 10; i++)
	{
		d1.push_back(i);
	}
	printDeque2(d1);

	//operator= 赋值
	deque<int>d2;
	d2 = d1;
	printDeque2(d2);

	//assign赋值
	deque<int>d3;
	d3.assign(d2.begin() + 1, d2.end() - 1);
	printDeque2(d3);

	deque<int>d4;
	d4.assign(10, 1);//赋值10个1
	printDeque2(d4);
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

赋值方式和vector容器一样；

#### 5.4deque容器大小操作

```c++
#include<iostream>
#include<deque>
using namespace std;

//deque容器大小操作
void printDeque3(const deque<int>& d)
{
	for (deque<int>::const_iterator it = d.begin(); it != d.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test03()
{
	deque<int>d1;
	for (int i = 0; i < 10; i++)
	{
		d1.push_back(i);
	}
	printDeque3(d1);

	//判断是否为空
	if(d1.empty())
	{
		cout << "d1为空" << endl;
	}
	else {
		cout << "d1不为空" << endl;
		cout << "d1的大小为：" << d1.size() << endl;
		//deque容器没有容量概念，可以无限存放数据
	}

	d1.resize(15, 1);//扩充的部分用1填充
	printDeque3(d1);

	d1.resize(5);
	printDeque3(d1);
}

int main()
{
	test03();
	system("pause");
	return 0;
}
```

==deque没有容量的概念；==

#### 5.5deque容器插入删除操作

两端插入删除：

```c++
push_back(elem);//尾插
push_front(elem);//头插
pop_back();//尾删
pop_front;//头删
```

指定位置插入删除：

```c++
insert(pos,elem);//
insert(pos,n,elem);//pos位置插入n个elem数据，无返回值
insert(pos,beg,end);//在pos位置插入[beg,end]之间的数据，无返回值
clear();//清除容器中所有数据
erase(beg,end);//删除[beg,end]区间数据，返回下一个数据的位置
erase(pos);//删除pos位置的数据，返回下一个数据的位置
```

```c++
#include<iostream>
#include<deque>
using namespace std;


void printDeque4(const deque<int>& d)
{
	for (deque<int>::const_iterator it = d.begin(); it != d.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
//两端操作
void test04()
{
	deque<int> d1;
	//尾插
	d1.push_back(10);
	d1.push_back(20);
	//头插
	d1.push_front(100);
	d1.push_front(200);
	printDeque4(d1);
	//尾删
	d1.pop_back();
	printDeque4(d1);
	//头删
	d1.pop_front();
	printDeque4(d1);
}
//指定位置插入删除
void test05()
{
	deque<int>d1;
	//尾插
	d1.push_back(10);
	d1.push_back(20);
	//头插
	d1.push_front(100);
	d1.push_front(200);
	printDeque4(d1);
	//insert插入
	d1.insert(d1.begin(), 1000);
	printDeque4(d1);
	d1.insert(d1.begin(), 2,10000);
	printDeque4(d1);
	//按照区间插入
	deque<int>d2;
	d2.push_back(1);
	d2.push_back(2);
	d2.push_back(3);
	d1.insert(d1.begin(), d2.begin(), d2.end());
	printDeque4(d1);
	//删除
	deque<int>::iterator it = d1.begin();
	it++;
	d1.erase(it);
	printDeque4(d1);
	//指定区间方式删除
	d1.erase(d1.begin() + 1, d1.end() - 1);
	printDeque4(d1);
	d1.clear();//清空
	printDeque4(d1);
}
int main()
{
	test04();
	test05();
	system("pause");
	return 0;
}
```

#### 5.6deque数据存取

```c++
#include<iostream>
#include<deque>
using namespace std;

void test06()
{
	deque<int>d;
	d.push_back(10);
	d.push_back(20);
	d.push_back(30);
	d.push_front(100);
	d.push_front(200);
	d.push_front(300);

	//通过[]方式访问元素
	for (int i = 0; i < d.size(); i++)
	{
		cout << d[i] << " ";
	}
	cout << endl;
	//通过at方式访问元素
	for (int i = 0; i < d.size(); i++)
	{
		cout << d.at(i)<< " ";
	}
	cout << endl;
    
    cout << "front=" << d.front() << endl;
	cout << "back=" << d.back() << endl;
}

int main()
{
	test06();
	system("pause");
	return 0;
}
```

#### 5.7deque容器排序

```c++
#include<iostream>
#include<deque>
#include<algorithm>
using namespace std;


void printDeque6(const deque<int>& d)
{
	for (deque<int>::const_iterator it = d.begin(); it != d.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test07()
{
	deque<int>d;
	d.push_back(10);
	d.push_back(20);
	d.push_back(30);
	d.push_front(100);
	d.push_front(200);
	d.push_front(300);
	printDeque6(d);

	//排序
	sort(d.begin(),d.end());//默认升序排序
	cout << "排序后：" << endl;
	printDeque6(d);
}

int main()
{
	test07();
	system("pause");
	return 0;
}
```

### 6.案例-评委打分

1. 创建五名选手，放到vector中
2. 遍历vector容器，取出来每一位选手，执行for循环，可以把10个评委打分存到deque容器中
3. sort算法对deque容器中的分数排序，去除最高分和最低分
4. deque容器遍历一遍，累加总分
5. 获取平均分

```c++
#include<iostream>
#include<vector>
#include<deque>
#include<string>
#include<algorithm>
#include<ctime>
using namespace std;

class Person
{
public:
	Person(string name, int score)
	{
		this->m_Name = name;
		this->m_Score = score;
	}
	string m_Name;//姓名
	int m_Score;//分数
};

void creatPerson(vector<Person>& v)
{
	string nameseed = "ABCDE";
	for (int i = 0; i < 5; i++)
	{
		string name = "选手";
		name += nameseed[i];

		int score = 0;
		Person p(name, score);
		//将创建的person对象放入容器
		v.push_back(p);
	}
}
//打分
void setScore(vector<Person>& v)
{
	for (vector<Person>::iterator it = v.begin(); it != v.end(); it++)
	{
		//将评委分数放入deque容器中
		deque<int>d;
		for (int i = 0; i < 10; i++)
		{
			int score = rand() % 41 + 60;//60-100
			d.push_back(score);
		}
	/*	cout << "选手：" << it->m_Name << "打分：" << endl;
		for (deque<int>::iterator dit = d.begin(); dit != d.end(); dit++)
		{
			cout << *dit << " ";
		}
		cout << endl;*/
		//排序
		sort(d.begin(), d.end());
		//去除最高最低分
		d.pop_back();
		d.pop_front();
		//取平均分
		int sum = 0;
		for (deque<int>::iterator dit = d.begin(); dit != d.end(); dit++)
		{
			sum += *dit;
		}
		int avg = sum / d.size();
		//将平均分赋值给选手
		it->m_Score = avg;
	}
}
//展示结果
void showScore(vector<Person>& v)
{
	for (vector<Person>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << "姓名：" << (*it).m_Name << "平均分：" << (*it).m_Score << endl;
	}
}
int main()
{
	srand((unsigned int)time(NULL));
	//创建五名选手
	vector<Person>v;//存放选手的容器
	creatPerson(v);

	//给五名选手打分
	setScore(v);
	//显示最后得分
	showScore(v);

	system("pause");
	return 0;
}
```

### 7.STL--stack容器

#### 7.1stack基本概念

stack（栈）是一种==先进后出==的数据结构，只有一个出口；

==不允许随机访问，不允许遍历行为；只能访问栈顶元素；==

#### 7.2stack常用接口

构造函数：

```c++
stack<T> stk;//stack采用模板类实现，stack对象的默认构造形式
stack(const stack &stk);//拷贝构造函数
```

赋值操作：

```c++
stack& operator=(const stack &stk);//重载等号操作符
```

数据存取：

```c++
push(elem);//向栈顶添加元素
pop();//从栈顶移除第一个元素
top();//返回栈顶元素
```

大小操作：

```c++
empty();//判断堆栈是否为空
size();//返回栈的大小
```

```c++
#include<iostream>
#include<stack>
using namespace std;

void test01()
{
	stack<int>s;

	s.push(10);
	s.push(20);
	s.push(30);
	s.push(40);
	
	while (!s.empty())
	{
		cout << "栈顶元素为：" << s.top() << endl;

		s.pop();
	}
	cout << "栈的大小为：" << s.size() << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

### 8.STL--queue容器

queue(队列)是一种先进先出的数据结构，有两个出口；

构造函数：

```c++
queue<T> que;//queue采用模板类实现，queue对象的默认构造形式
queue(const queue &que);//拷贝构造函数
```

赋值操作：

```c++
queue& operator=(const queue &que);//重载等号操作符
```

数据存取：

```c++
push(elem);//往队尾添加元素
pop();//从队头移除第一个元素
back();//返回最后一个元素
front();//返回第一个元素
```

大小操作：

```c++
empty();//判断堆栈是否为空
size();//返回栈的大小
```

```c++
#include<iostream>
#include<queue>
using namespace std;

class Person
{
public:
	Person(string name,int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}
	string m_Name;
	int m_Age;
};

void test()
{
	queue<Person>q;

	Person p1("唐僧", 30);
	Person p2("孙悟空", 1000);
	Person p3("猪八戒", 900);
	Person p4("沙僧", 800);

	q.push(p1);
	q.push(p2);
	q.push(p3);
	q.push(p4);

	//判断队列，查看队头队尾
	while (!q.empty())
	{
		cout << "队头元素--姓名：" << q.front().m_Name << "年龄：" << q.front().m_Age << endl;
		cout << "队尾元素--姓名：" << q.back().m_Name << "年龄：" << q.back().m_Age << endl;
		q.pop();
	}
}
int main()
{
	test();
	system("pause");
	return 0;
}
```

### 9.STL--list容器

#### 9.1list基本概念

list容器：链表

结点的组成：一个是存储数据元素的数据域，另一个是存储下一代结点地址的指针域（一个指向前一结点，一个指向后一个结点）；

STL中的链表是一个双向循环链表；

list的优点：

- 采用动态存储分配，不会造成内存浪费和溢出
- 链表执行插入和删除操作十分方便，修改指针即可，不需要移动大量元素

list的缺点：

- 链表灵活，但是空间(指针域)和事件（遍历）额外耗费较大

list有一个重要的性质，插入操作和删除操作都不会造成原有list迭代器的实现，这在vector是不成立的；

STL中list和vector是两个最常被使用的容器，各有优劣；

#### 9.2list构造函数

```c++
#include<iostream>
#include<list>
using namespace std;

//list容器构造函数
void printList(const list<int>&L)
{
	for (list<int>::const_iterator it = L.begin(); it != L.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test01()
{
	list<int>L1;
	//添加数据
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	printList(L1);

	list<int>L2(L1.begin(),L1.end());
	printList(L2);

	list<int>L3(L2);
	printList(L3);

	list<int>L4(10, 1);//10个1
	printList(L4);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 9.3list容器赋值与交换

```c++
#include<iostream>
#include<list>
using namespace std;

void printList1(const list<int>& L)
{
	for (list<int>::const_iterator it = L.begin(); it != L.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

void test02()
{
	list<int>L1;
	//添加数据
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	printList1(L1);

	//赋值
	list<int>L2;
	L2 = L1;  //operator =方式赋值
	printList1(L2);

	list<int>L3;
	L3.assign(L2.begin(), L2.end());
	printList1(L3);

	list<int>L4;
	L4.assign(10, 1);//10个1
	printList1(L4);
}

void test03()
{
	list<int>L1;
	//添加数据
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	printList1(L1);

	list<int>L2;
	L2.assign(10, 100);
	cout << "交换前：" << endl;
	printList1(L1);
	printList1(L2);
	//交换
	L1.swap(L2);
	cout << "交换后：" << endl;
	printList1(L1);
	printList1(L2);
}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

#### 9.4list容器大小操作

```c++
#include<iostream>
#include<list>
using namespace std;

void printList2(const list<int>& L)
{
	for (list<int>::const_iterator it = L.begin(); it != L.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test04()
{
	list<int>L1;
	//添加数据
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	printList2(L1);

	if (L1.empty())
	{
		cout << "L1为空" << endl;
	}
	else
	{
		cout << "L1不为空" << endl;
		cout << "L1元素个数：" << L1.size() << endl;
	}

	L1.resize(10, 1000);
	printList2(L1);
	L1.resize(2);
	printList2(L1);
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 9.5list容器插入和删除

==remove(elem);//移除list中所有与elem匹配的元素==

```c++
#include<iostream>
#include<list>
using namespace std;

void printList3(const list<int>& L)
{
	for (list<int>::const_iterator it = L.begin(); it != L.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test05()
{
	list<int>L1;
	//添加数据,尾插
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	//头插
	L1.push_front(100);
	L1.push_front(200);
	L1.push_front(300);
	printList3(L1);
	//尾删
	L1.pop_back();
	//头删
	L1.pop_front();

	//insert插入
	L1.insert(L1.begin(), 1000);
	printList3(L1);
	//erase删除
	L1.erase(L1.begin());
	printList3(L1);

	L1.assign(10, 10000);
	printList3(L1);
    
	L1.remove(10000);
	printList3(L1);
}

int main()
{
	test05();
	system("pause");
	return 0;
}
```

#### 9.6list容器数据存取

==list链表只能顺序存取，不能随机存取；==

```c++
//迭代器不支持随机访问
	list<int>::iterator it = L1.begin();
	it++;//没问题++--都是可以的
	//it = it + 1;//报错，不支持随机访问
```

```c++
front();//返回第一个
back();//返回最后一个
```

```c++
#include<iostream>
#include<list>
using namespace std;

void test06()
{

	list<int>L1;
	//添加数据,尾插
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	//头插
	L1.push_front(100);
	L1.push_front(200);
	L1.push_front(300);

	//不可以用[]方式访问list容器中的元素
	cout << "第一个元素为：" << L1.front()<<endl;
	cout << "最后一个元素为：" << L1.back() << endl;

	//迭代器不支持随机访问
	list<int>::iterator it = L1.begin();
	it++;//没问题++--都是可以的
	//it = it + 1;//报错，不支持随机访问
}
int main()
{
	test06();
	system("pause");
	return 0;
}
```

#### 9.7list反转和排序

```c++
reverse();//反转链表
sort();//链表排序
```

```c++
#include<iostream>
#include<list>
using namespace std;

void printList6(const list<int>& L)
{
	for (list<int>::const_iterator it = L.begin(); it != L.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
bool myCompare(int num1, int num2)
{
	return num1 > num2;
}
void test07()
{
	list<int>L1;
	//添加数据,尾插
	L1.push_back(10);
	L1.push_back(20);
	L1.push_back(30);
	L1.push_back(40);
	//头插
	L1.push_front(100);
	L1.push_front(200);
	L1.push_front(300);
	printList6(L1);
	
	L1.reverse();
	printList6(L1);
	//升序
	L1.sort();
	printList6(L1);
	//降序
	L1.sort(myCompare);
	printList6(L1);
}

int main()
{
	test07();
	system("pause");
	return 0;
}
```

#### 9.8排序案例

将person自定义数据类型进行排序，属性有姓名、年龄、身高；

排序规则：按照年龄升序排列，如果年龄相同则按升高降序排列；

```c++
#include<iostream>
#include<list>
using namespace std;

class Person
{
public:
	Person(string name,int age,int height)
	{
		this->m_Age = age;
		this->m_Height = height;
		this->m_Name = name;
	}

	string m_Name;
	int m_Age;
	int m_Height;
};

//指定排序规则
bool comparePerson(Person &p1,Person &p2)
{
	//按照年龄升序
	if (p1.m_Age == p2.m_Age)
	{
		//年龄相同按照身高降序
		return p1.m_Height > p2.m_Height;
	}
	else {
		return p1.m_Age < p2.m_Age;
	}
}
void test08()
{
	list<Person>L;

	Person p1("刘备", 35, 175);
	Person p2("曹操", 45, 185);
	Person p3("关羽", 35, 165);
	Person p4("张飞", 65, 195);
	Person p5("赵云", 35, 155);
	Person p6("马超", 55, 177);
	Person p7("孙权", 25, 170);

	L.push_back(p1);
	L.push_back(p2);
	L.push_back(p3);
	L.push_back(p4);
	L.push_back(p5);
	L.push_back(p6);
	L.push_back(p7);

	for (list<Person>::iterator it = L.begin(); it != L.end(); it++)
	{
		cout << "姓名：" << (*it).m_Name << "年龄：" << it->m_Age << "身高：" << it->m_Height << endl;
	}
	//排序
	cout << "排序后：" << endl;

	L.sort(comparePerson);
	for (list<Person>::iterator it = L.begin(); it != L.end(); it++)
	{
		cout << "姓名：" << (*it).m_Name << "年龄：" << it->m_Age << "身高：" << it->m_Height << endl;
	}
}

int main()
{
	test08();
	system("pause");
	return 0;
}
```

### 10.STL--set/multiset容器

#### 10.1set(集合)基本概念

简介：

- ==所有元素都会在插入时自动被排序==

本质：

- ==set/multiset属于关联式容器，底层结构是用二叉树实现==

set/multiset区别：

- ==set不允许容器中有重复的元素==
- ==multiset允许容器中有重复的元素==

#### 10.2set构造和赋值

```c++
#include<iostream>
#include<set>
using namespace std;


void printSet(set<int>& s)
{
	for (set<int>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test01()
{
	set<int> s1;
	//插入数据，只有insert方式
	s1.insert(10);
	s1.insert(20);
	s1.insert(30);
	s1.insert(40);
	s1.insert(30);
	//遍历容器
	//set容器特点：所有元素插入时自动被排序
	//set容器不允许插入重复值
	printSet(s1);

	//拷贝构造
	set<int>s2(s1);
	printSet(s2);

	//赋值
	set<int>s3;
	s3 = s2;
	printSet(s3);
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 10.3set容器大小和交换

==不支持resize==；

```c++
#include<iostream>
#include<set>
using namespace std;

void printSet2(set<int>& s)
{
	for (set<int>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
//大小
void test02()
{
	set<int> s1;
	//插入数据，只有insert方式
	s1.insert(10);
	s1.insert(20);
	s1.insert(30);
	s1.insert(40);
	printSet2(s1);

	//判断是否为空
	if (s1.empty())
	{
		cout << "s1为空" << endl;
	}
	else {
		cout << "s1不为空" << endl;
		cout << "s1的大小为：" << s1.size() << endl;
	}
}

//交换
void test03()
{
	set<int> s1;
	//插入数据，只有insert方式
	s1.insert(10);
	s1.insert(20);
	s1.insert(30);
	s1.insert(40);
	s1.insert(30);
	
	set<int> s2;
	//插入数据，只有insert方式
	s2.insert(100);
	s2.insert(200);
	s2.insert(300);
	s2.insert(400);
    
	cout << "交换前：" << endl;
	printSet2(s1);
	printSet2(s2);
	cout << "交换后：" << endl;
	s1.swap(s2);
	printSet2(s1);
	printSet2(s2);
}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

#### 10.4插入和删除

```c++
#include<iostream>
#include<set>
using namespace std;

void printSet3(set<int>& s)
{
	for (set<int>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}
void test04()
{
	set<int>s1;

	s1.insert(10);
	s1.insert(20);
	s1.insert(30);
	s1.insert(40);
	printSet3(s1);

	//删除
	s1.erase(s1.begin());
	printSet3(s1);

	s1.erase(30);
	printSet3(s1);

	s1.erase(s1.begin(), s1.end());//清空
	printSet3(s1);
	s1.clear();//清空
	printSet3(s1);
}
int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 10.5set查找和统计

```c++
find(key);//查找key是否存在，存在则返回迭代器；不存在则返回end()
count(elem);//对于set而言结果只能是0或者1
```

```c++
#include<iostream>
#include<set>
using namespace std;

void test05()
{
	set<int>s1;

	s1.insert(10);
	s1.insert(20);
	s1.insert(30);
	s1.insert(40);
	//查找
	set<int>::iterator pos = s1.find(30);
	if (pos != s1.end())
	{
		cout << "找到该元素" << endl;
	}
	else
	{
		cout << "未找到该元素" << endl;
	}
	//统计个数
	int num = s1.count(20);
	cout << "num=" << num << endl;
}

int main()
{
	test05();
	system("pause");
	return 0;
}
```

#### 10.6set和multiset区别

区别：

- ==set不可以插入重复数据，multiset可以；==
- set插入数据的同时会返回插入结果，表示是否插入成功；
- multiset不会检测数据，因此可以插入重复数据；

```c++
#include<iostream>
#include<set>
using namespace std;

void test06()
{
	set<int>s1;
 	 pair<set<int>::iterator,bool> ret=s1.insert(10);
	 if (ret.second)
	 {
		 cout << "第一次插入成功" << endl;
	 }
	 else
	 {
		 cout << "第一次插入失败" << endl;
	 }
	 ret = s1.insert(10);
	 if (ret.second)
	 {
		 cout << "第二次插入成功" << endl;
	 }
	 else
	 {
		 cout << "第二次插入失败" << endl;
	 }

	 multiset<int>ms;
	 ms.insert(10);
	 ms.insert(10);
	 for (multiset<int>::iterator it = ms.begin(); it != ms.end(); it++)
	 {
		 cout << *it << " ";
	 }
	 cout << endl;
}


int main()
{
	test06();
	system("pause");
	return 0;
}
```

#### 10.7pair对组

成对出现的数据，利用对组可以返回两个数据；

```c++
pair<type,type>p(value1,value2);
pair<type,type>p=make pair(value1,value2);
```

```c++
#include<iostream>
#include<string>
using namespace std;

void test07()
{
	//第一种方式
	pair<string, int>p("TOM", 20);
	cout << "姓名：" << p.first << "年龄" << p.second << endl;

	//第二种方式
	pair<string, int>p2 = make_pair("JOHN", 19);
	cout << "姓名：" << p2.first << "年龄" << p2.second << endl;

}

int main()
{
	test07();
	system("pause");
	return 0;
}
```

#### 10.8set容器排序

- set容器默认排序规则为从小到大，掌握如何改变排序规则
- 利用仿函数，可以改变排序规则

```c++
//仿函数
class MyCompare
{
public:
	bool operator()(int v1,int v2) const
	{
		return v1 > v2;
	}
};
```

==仿函数部分const必须要加，不然会VS编译错误；==

```c++
#include<iostream>
#include<set>
using namespace std;

//set存放内置数据类型，改变排序规则
//仿函数
class MyCompare
{
public:
	bool operator()(int v1,int v2) const
	{
		return v1 > v2;
	}
};
void test08()
{
	set<int>s1;
	s1.insert(10);
	s1.insert(30);
	s1.insert(40);
	s1.insert(20);
	s1.insert(50);
	for (set<int>::iterator it = s1.begin(); it != s1.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;

	//指定排序规则为从大到小,插入之前定制规则
	set<int,MyCompare>s2;
	s2.insert(10);
	s2.insert(30);
	s2.insert(40);
	s2.insert(20);
	s2.insert(50);
	for (set<int>::iterator it = s2.begin(); it != s2.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

int main()
{
	test08();
	system("pause");
	return 0;
}
```

set容器排序，存放自定义数据类型

```c++
#include<iostream>
#include<set>
using namespace std;

class Person
{
public:
	Person(string name, int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}
	string m_Name;
	int m_Age;
};

void test09()
{
	set<Person>s;
	Person p1("刘备", 24);
	Person p2("赵云", 14);
	Person p3("黄忠", 54);
	Person p4("关羽", 34);

	s.insert(p1);
	s.insert(p2);
	s.insert(p3);
	s.insert(p4);
	for (set<Person>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << "姓名：" << it->m_Name << "年龄：" << it->m_Age << endl;
	}
}

int main()
{
	test09();
	system("pause");
	return 0;
}
```

```c++
#include<iostream>
#include<set>
using namespace std;

class Person
{
public:
	Person(string name, int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}
	string m_Name;
	int m_Age;
};
class comparePerson
{
public:
	bool operator()(const Person& p1, const Person& p2) const
	{
		return p1.m_Age > p2.m_Age;
	}
};
void test09()
{
	//自定义数据类型都会指定排序规则
	set<Person,comparePerson>s;
	Person p1("刘备", 24);
	Person p2("赵云", 14);
	Person p3("黄忠", 54);
	Person p4("关羽", 34);

	s.insert(p1);
	s.insert(p2);
	s.insert(p3);
	s.insert(p4);
	for (set<Person>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << "姓名：" << it->m_Name << "年龄：" << it->m_Age << endl;
	}
}

int main()
{
	test09();
	system("pause");
	return 0;
}
```

### 11.STL--map/multimap容器

使用率仅次于vector、list；

#### 11.1map基本概念

简介：

- map中所有元素都是pair
- pair中第一个元素为key（键值），起索引作用，第二个元素为value（实值）
- 所有元素都会根据元素的键值自动排序

本质：

- map/multimap属于关联式容器，底层结构用二叉树实现

优点：

- 可以通过key值快速找到value值

map和multimap区别：

- map不允许容器中有重复key值元素
- multimap允许容器中有重复的key值元素

#### 11.2map构造与赋值

```c++
#include<iostream>
#include<map>
using namespace std;


void printMap(map<int, int>& m)
{
	for (map<int, int>::iterator it = m.begin(); it != m.end(); it++)
	{
		cout << "key=" << it->first << "value=" << it->second << endl;
	}
}
void test01()
{
	//创建map容器
	map<int, int>m;
	//按key值排序
	m.insert(pair<int, int>(1, 10));
	m.insert(pair<int, int>(2, 10));//键值必须不同，实值可以相同
	m.insert(pair<int, int>(3, 20));
	m.insert(pair<int, int>(4, 20));
	
	printMap(m);
	//拷贝构造
	map<int, int>m2(m);
	printMap(m2);

	//赋值
	map<int, int>m3;
	m3 = m2;
	printMap(m3);
}

int main()
{
	test01();
	system("pause");
	return 0;

}
```

#### 11.3map大小和交换

```c++
#include<iostream>
#include<map>
using namespace std;
//大小
void test02()
{
	map<int, int>m1;
	m1.insert(pair<int, int>(1, 10));
	m1.insert(pair<int, int>(2, 20));
	m1.insert(pair<int, int>(3, 30));
	m1.insert(pair<int, int>(4, 40));

	if (m1.empty())
	{
		cout << "m1为空" << endl;
	}
	else
	{
		cout << "m1不为空" << endl;
		cout << "m1大小为：" << m1.size() << endl;
	}
}
void printMap1(map<int, int>& m)
{
	for (map<int, int>::iterator it = m.begin(); it != m.end(); it++)
	{
		cout << "key=" << it->first << "value=" << it->second << endl;
	}
}
//交换
void test03()
{
	map<int, int>m1;
	m1.insert(pair<int, int>(1, 10));
	m1.insert(pair<int, int>(2, 20));
	m1.insert(pair<int, int>(3, 30));
	m1.insert(pair<int, int>(4, 40));

	map<int, int>m2;
	m2.insert(pair<int, int>(1, 20));
	m2.insert(pair<int, int>(2, 30));
	m2.insert(pair<int, int>(3, 40));
	m2.insert(pair<int, int>(4, 50));

	cout << "交换前：" << endl;
	printMap1(m1);
	printMap1(m2);

	m1.swap(m2);
	cout << "交换后：" << endl;
	printMap1(m1);
	printMap1(m2);

}
int main()
{
	test02();
	test03();
	system("pause");
	return 0;
}
```

#### 11.4map插入和删除

```c++
#include<iostream>
#include<map>
using namespace std;
void printMap2(map<int, int>& m)
{
	for (map<int, int>::iterator it = m.begin(); it != m.end(); it++)
	{
		cout << "key=" << it->first << "value=" << it->second << endl;
	}
}
void test04()
{
	map<int, int>m1;
	//插入
	//第一种
	m1.insert(pair<int, int>(1, 10));

	//第二种
	m1.insert(make_pair(2, 20));

	//第三种
	m1.insert(map<int, int>::value_type(3, 30));

	//第四种
	m1[4] = 40;

	printMap2(m1);

	//删除
	m1.erase(m1.begin());
	printMap2(m1);

	m1.erase(2);//按key值删除
	printMap2(m1);

	m1.erase(m1.begin(), m1.end());//清空
	m1.clear();//清空
	printMap2(m1);

}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 11.5map查找和统计

```c++
#include<iostream>
#include<map>
using namespace std;

void test05()
{
	//查找
	map<int, int>m;
	m.insert(pair<int, int>(1, 10));
	m.insert(pair<int, int>(2, 20));
	m.insert(pair<int, int>(3, 30));
	m.insert(pair<int, int>(4, 40));

	map<int, int>::iterator pos = m.find(3);

	if (pos != m.end())
	{
		cout << "查到了元素key=" << pos->first << "value=" << pos->second << endl;

	}
	else
	{
		cout << "未找到元素" << endl;
	}

	//统计
	//map不允许插入重复元素，multimap可以
	int num = m.count(3);
	cout << "num=" << num << endl;
}

int main()
{
	test05();
	system("pause"); 
	return 0;
}
```

#### 11.6map容器排序

map容器默认排序规则为：按照key值进行从小到大排序，掌握如何改变排序规则；

利用仿函数，可以改变排序规则；

```c++
#include<iostream>
#include<map>
using namespace std;

class myCompare
{
public:
	bool operator()(int v1,int v2) const
	{
		return v1 > v2;
	}
};

void test06()
{
	map<int, int>m;
	m.insert(make_pair(1, 10));
	m.insert(make_pair(2, 20));
	m.insert(make_pair(3, 30));
	m.insert(make_pair(4, 40));
	m.insert(make_pair(5, 50));

	for (map<int, int>::iterator it = m.begin(); it != m.end(); it++)
	{
		cout << "key=" << it->first 
			<< "	value=" << it->second << endl;
	}
	map<int, int,myCompare>m1;
	m1.insert(make_pair(1, 10));
	m1.insert(make_pair(2, 20));
	m1.insert(make_pair(3, 30));
	m1.insert(make_pair(4, 40));
	m1.insert(make_pair(5, 50));
	for (map<int, int>::iterator it = m1.begin(); it != m1.end(); it++)
	{
		cout << "key=" << it->first
			<< "	value=" << it->second << endl;
	}
}

int main()
{
	test06();
	system("pause");
	return 0;
}
```

### 12.案例--员工分组

#### 12.1案例描述

- 员工信息有：姓名、工资组成、部门分为策划、美术、研发
- 随机给10位员工分配部门和工资
- 通过multimap进行信息的插入 key(部门编号)value(员工)
- 分部门显示员工信息

#### 12.2源代码

```c++
#include<iostream>
#include<vector>
#include<string>
#include<map>
#include<ctime>
using namespace std;
#define CEHUA 0
#define MEISHU 1
#define YANFA 2
class Worker
{
public:

	string m_Name;
	int m_Salary;
};

void createWorker(vector<Worker>& v)
{
	string nameseed = "ABCDEFGHIJ";
	for (int i = 0; i < 10; i++)
	{
		Worker worker;
		worker.m_Name = "员工";
		worker.m_Name += nameseed[i];

		worker.m_Salary = rand() % 10000 + 10000;
		//将员工放入容器
		v.push_back(worker);
	}
}
//员工分组
void setGroup(vector<Worker>& v, multimap<int, Worker>& m)
{
	for (vector<Worker>::iterator it = v.begin(); it != v.end(); it++)
	{
		//产生部门随机数
		int deptId = rand() % 3;
		//将员工插入到分组
		m.insert(make_pair(deptId, *it));
	}
}
void showWorkerByGroup(multimap<int,Worker>&m)
{

	cout << "策划部门：" << endl;
	multimap<int, Worker>::iterator pos = m.find(CEHUA);
	int count = m.count(CEHUA);
	int index = 0;
	for (;pos != m.end() && index < count; pos++,index++)
	{
		cout << "姓名：" << pos->second.m_Name 
			<< "工资："<< pos->second.m_Salary << endl;
	}

	cout << "美术部门：" << endl;
	pos = m.find(MEISHU);
	count = m.count(MEISHU);
	index = 0;
	for (; pos != m.end() && index < count; pos++, index++)
	{
		cout << "姓名：" << pos->second.m_Name
			<< "工资：" << pos->second.m_Salary << endl;
	}
	cout << "研发部门：" << endl;

	pos = m.find(YANFA);
	count = m.count(YANFA);
	index = 0;
	for (; pos != m.end() && index < count; pos++, index++)
	{
		cout << "姓名：" << pos->second.m_Name
			<< "工资：" << pos->second.m_Salary << endl;
	}

}
int main()
{
	srand((unsigned int)time(NULL));
	//创建员工
	vector<Worker>vWorker;
	createWorker(vWorker);

	//分组
	multimap<int, Worker>mWorker;
	setGroup(vWorker,mWorker);

	//分组显示员工
	showWorkerByGroup(mWorker);
	system("pause");
	return 0;
}
```

### 13.STL--函数对象

#### 13.1函数对象

概念：

- 重载函数调用操作符的类，其对象称为函数对象
- 函数对象使用重载的()时，行为类似函数调用，也叫仿函数

本质：

函数对象（仿函数）是一个类，不是一个函数；

**函数对象使用：**

特点：

- ==函数对象在使用时，可以像普通函数那样调用，可以有参数，可以有返回值==
- ==函数对象超出普通函数的概念，函数对象可以有自己的状态==
- ==函数对象可以作为函数传递==

```c++
#include<iostream>
using namespace std;

//函数对象--仿函数
//函数对象在使用时，可以像普通函数那样调用，可以有参数，可以有返回值
class MyAdd
{
public:
	int operator()(int v1, int v2) const
	{
		return v1 + v2;
	}
};
void test01()
{
	MyAdd ma;
	cout << ma(10, 10) << endl;
}
//函数对象超出普通函数的概念，函数对象可以有自己的状态
class MyPrint
{
public:
	void operator()(string test)
	{
		cout << test << endl;
		this->count++;
	}
	int count=0;
};
void test02()
{
	MyPrint mp;
	mp("hello world");
	mp("hello world");
	mp("hello world");
	mp("hello world");
	mp("hello world");

	cout << "myprint调用次数：" << mp.count << endl;
}
//函数对象可以作为函数传递
void doPrint(MyPrint &mp,string test)
{
	mp(test);
}
void test03()
{
	MyPrint mp1;
	doPrint(mp1, "hello c++");
}
int main()
{
	test01();
	test02();
	test03();
	system("pause");
	return 0;
}
```

#### 13.2谓词

概念：

- 返回bool类型的仿函数称为谓词
- 如果operator()接受一个参数，那么叫做一元谓词
- 如果operator()接受两个参数，那么叫做二元谓词

**一元谓词：**

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

class GreaterFive
{
public:
	bool operator()(int val)
	{
		return val > 5;
	}
};
void test04()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}
	//查找容器内 有没有大于5的数字
	//GreaterFive()匿名函数对象
	vector<int>::iterator it = find_if(v.begin(), v.end(),GreaterFive());
	if (it == v.end())
	{
		cout << "未找到" << endl;
	}
	else
	{
		cout << "找到了大于5的数字为：" << *it << endl;
	}
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

**二元谓词**

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

class myCompare
{
public:
	bool operator()(int v1, int v2)
	{
		return v1 > v2;
	}
};
void test05()
{
	vector<int>v;
	v.push_back(10);
	v.push_back(40);
	v.push_back(30);
	v.push_back(50); 
	v.push_back(20);

	sort(v.begin(), v.end());
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << endl;
	}
	cout << endl;
	//使用函数对象，改变算法策略，变为排序规则从大到小
	sort(v.begin(), v.end(), myCompare());
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

int main()
{
	test05();
	system("pause"); 
	return 0;
}
```

#### 13.3内建函数对象

分类：

- 算术仿函数
- 关系仿函数
- 逻辑仿函数

##### 13.3.1算术仿函数

功能：实现四则运算；

仿函数原型：

```c++
template<class T> T plus<T>;//加法仿函数
template<class T> T minus<T>;//减法仿函数
template<class T> T multiplies<T>;//乘法仿函数
template<class T> T divides<T>;//除法仿函数
template<class T> T modules<T>;//取模仿函数
template<class T> T negate<T>;//取反仿函数（一元运算）
```

```c++
#include<iostream>
using namespace std;
#include<functional>
//negate 一元仿函数 取反仿函数
void test06()
{
	negate<int>n;
	cout << n(50) << endl;
}
//plus 二元仿函数 加法
void test07()
{
	plus<int>p;
	cout << p(10, 20) << endl;
}
int main()
{
	test06();
	test07();
	system("pause");
	return 0;
}
```

##### 13.3.2关系仿函数

功能：实现关系对比；

仿函数原型：

```c++
template<class T> bool equal_to<T>;//等于
template<class T> bool not_equal_to<T>;//不等于
template<class T> bool greater<T>;//大于
template<class T> bool greater_equal<T>;//大于等于
template<class T> bool less<T>;//小于
template<class T> bool less_equal<T>;//小于等于
```

##### 13.3.3逻辑仿函数

```c++
template<class T> bool logical_and<T>;//逻辑与
template<class T> bool logical_or<T>;//逻辑或
template<class T> bool logical_not<T>;//逻辑非
```

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>
#include<functional>
void test09()
{
	vector<bool>v;
	v.push_back(true);
	v.push_back(true);
	v.push_back(false);
	v.push_back(false);

	for (vector<bool>::iterator it = v.begin(); it != v.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;

	//利用逻辑非 将容器v搬运到容器v2中，并执行取反操作
	vector<bool>v2;
	v2.resize(v.size());

	transform(v.begin(), v.end(), v2.begin(),logical_not<bool>());
	for (vector<bool>::iterator it = v2.begin(); it != v2.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

int main()
{
	test09();
	system("pause");
	return 0;
}
```

### 14.STL常用算法

概述：

- 算法主要由头文件`<algorithm><functional><numeric>`组成
- `<algorithm>`是所有STL头文件中最大的一个，范围涉及到比较、交换、查找、遍历操作、复制、修改等；
- `<numeric>`体积很小，只包括几个在序列上面进行简单数学运算的模板函数；
- `<functional>`定义了一些模板类，用以声明函数对象；

#### 14.1常用遍历算法

`for_each(iterator beg,iterator end,_func);`//遍历容器

//beg开始迭代器；//end结束迭代器；//_func函数或者函数对象；

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

//普通函数
void print01(int val)
{
	cout << val << " ";
}
//函数对象
class print02
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}

	for_each(v.begin(), v.end(), print01);
	cout << endl;
	for_each(v.begin(), v.end(), print02());
	cout << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

`transform(iterator beg1,iterator end1,iterator beg2,_func)`

//beg1源容器开始迭代器；//end1源容器结束迭代器；

//beg2 目标容器开始迭代器；//_func 函数或者函数对象

```c++
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;

class Transform
{
public:
	int operator()(int v)
	{
		return v;
	}
};
class print03
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};
void test02()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}

	vector<int>vTarget;
	vTarget.resize(v.size());//目标容器需要提前开辟空间
	transform(v.begin(), v.end(), vTarget.begin(), Transform());
	for_each(vTarget.begin(), vTarget.end(), print03());
	cout << endl;
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 14.2常用查找算法

##### 14.2.1 find

功能：查找指定元素，找到返回指定元素的迭代器，找不到返回结束迭代器end();

函数原型：`find(iterator beg,iterator end,calue);`

==查找自定义数据类型时需要重载==号，不然不指定怎么比较；==

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<string>

//查找 内置数据类型
void test01()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}
	//find 查找容器中是否有5这个元素
	vector<int>::iterator it = find(v.begin(), v.end(), 5);
	if (it == v.end())
	{
		cout << "未找到" << endl;
	}
	else
	{
		cout << "找到" << *it << endl;
	}
}

//自定义数据类型
class Person
{
public:
	Person(string name, int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}

	//重载==符号，让底层find知道如何对比数据
	bool operator==(const Person &p)
	{
		if (this->m_Age == p.m_Age && this->m_Name == p.m_Name)
		{
			return true;
		}
		else
		{
			return false;
		}
	}
	string m_Name;
	int m_Age;
};

void test02()
{
	vector<Person>v;

	Person p1("a", 10);
	Person p2("c", 20);
	Person p3("s", 30);
	Person p4("d", 40);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);

	vector<Person>::iterator it= find(v.begin(), v.end(), p2);
	if (it == v.end())
	{
		cout << "未找到" << endl;
	}
	else
	{
		cout << "找到,姓名：" << it->m_Name<<"年龄："<<it->m_Age << endl;
	}
}

int main()
{
	test01();
	test02();
	system("pause");
	return 0;
}
```

##### 14.2.2find_if

`find_if(iterator beg,iterator end,_Pred);`

//按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置；

==//_Pred函数或者谓词(返回bool类型的仿函数)==；

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<string>

class GreaterFive
{
public:
	bool operator()(int val)
	{
		return val > 5;
	}
};
//查找 内置数据类型
void test03()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}
	//find 查找容器中是否有5这个元素
	vector<int>::iterator it = find_if(v.begin(), v.end(), GreaterFive());
	if (it == v.end())
	{
		cout << "未找到" << endl;
	}
	else
	{
		cout << "找到" << *it << endl;
	}
}

//自定义数据类型
class Person2
{
public:
	Person2(string name, int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}

	//重载==符号，让底层find知道如何对比数据
	bool operator==(const Person2& p)
	{
		if (this->m_Age == p.m_Age && this->m_Name == p.m_Name)
		{
			return true;
		}
		else
		{
			return false;
		}
	}
	string m_Name;
	int m_Age;
};

class Greater20
{
public:
	bool operator()(Person2 &p)
	{
		return p.m_Age > 20;
	}
};
void test04()
{
	vector<Person2>v;

	Person2 p1("a", 10);
	Person2 p2("c", 20);
	Person2 p3("s", 30);
	Person2 p4("d", 40);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);

	vector<Person2>::iterator it = find_if(v.begin(), v.end(),Greater20());
	if (it == v.end())
	{
		cout << "未找到" << endl;
	}
	else
	{
		cout << "找到,姓名：" << it->m_Name << "年龄：" << it->m_Age << endl;
	}
}

int main()
{
	test03();
	test04();
	system("pause");
	return 0;
}
```

##### 14.2.3adjacent_find

查找==相邻重复==元素；

`adjacent_find(iterator beg,iterator end);`

查找成功返回相邻重复元素中第一个元素迭代器，失败则返回end；

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>


void test05()
{
	vector<int>v;
	v.push_back(0);
	v.push_back(2);
	v.push_back(0);
	v.push_back(3);
	v.push_back(3);
	v.push_back(1);
	v.push_back(4);

	vector<int>::iterator pos = adjacent_find(v.begin(), v.end());
	if (pos == v.end())
	{
		cout << "未找到相邻重复元素" << endl;
	}
	else
	{
		cout << "找到了相邻重复元素" << endl;
	}
}
int main()
{
	test05();
	system("pause");
	return 0;
}
```

##### 14.2.4 binary_search

功能：查找指定元素是否存在；

`bool binary_search(iterator beg,iterator end,value);`

==必须在有序序列中使用，无序序列不可以用；==

//查找指定元素，查到返回true，否则返回false;

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>
void test06()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}

 	bool ret = binary_search(v.begin(), v.end(), 9);
	if (ret)
	{
		cout << "找到了元素" << endl;
	}
	else
	{
		cout << "未找到元素" << endl;
	}
}

int main()
{
	test06();
	system("pause");
	return 0;
}
```

##### 14.2.5count

功能：统计元素个数；

`count(iterator beg,iterator end,value);`

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>
//内置数据类型统计
//void test07()
//{
//	vector<int>v;
//	v.push_back(10);
//	v.push_back(20);
//	v.push_back(10);
//	v.push_back(20);
//	v.push_back(10);
//	v.push_back(40);
//	v.push_back(10);
//	v.push_back(10);
//
//	int num = count(v.begin(), v.end(), 10);
//
//	cout << "元素10个数为：" << num << endl;
//}
//自定义数据类型
class Person5
{
public:
	Person5(string name, int age)
	{
		this->m_Age = age;
		this->m_Name = name;
	}

	bool operator==(const Person5& p)
	{
		if (this->m_Age == p.m_Age)
		{
			return true;
		}
		else
		{
			return false;
		}
	}
	string m_Name;
	int m_Age;
};
void test08()
{
	vector<Person5>v1;
	Person5 p1("刘备", 35);
	Person5 p2("关羽", 25);
	Person5 p3("张飞", 15);
	Person5 p4("赵云", 35);
	Person5 p5("曹操", 5);
	Person5 p6("孙权", 35);
	Person5 p7("黄忠", 35);

	v1.push_back(p1);
	v1.push_back(p2);
	v1.push_back(p3);
	v1.push_back(p4);
	v1.push_back(p5);
	v1.push_back(p6);
	v1.push_back(p7);

	Person5 p("诸葛亮", 35);

	int num = count(v1.begin(), v1.end(), p);
	cout << "和诸葛亮同岁的人个数为：" << num << endl;

}
int main()
{
	//test07();
	test08();
	system("pause");
	return 0;
}
```

14.2.6 count_if

功能：按条件统计元素个数

`count_if(iterator beg,iterator end,_Perd);`

//_Perd谓词

```
```

#### 14.3常用排序算法

##### 14.3.1 sort

`sort(iterator beg,iterator end,_Perd);`

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

void myPrint(int val)
{
	cout << val << " ";
}
void test01()
{
	vector<int>v;
	v.push_back(10);
	v.push_back(50);
	v.push_back(30);
	v.push_back(140);
	v.push_back(20);
	v.push_back(40);

	//升序
	sort(v.begin(), v.end());
	for_each(v.begin(), v.end(), myPrint);
	cout << endl;

	//降序
	sort(v.begin(), v.end(), greater<int>());
	for_each(v.begin(), v.end(), myPrint);
	cout << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 14.3.2 random_shuffle

功能：洗牌，指定范围内的元素随机调整次序

`random_shuffle(iterator beg,iterator end);`

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>
#include<ctime>

void myPrint2(int val)
{
	cout << val << " ";
}
void test02()
{
	srand((unsigned int)time(NULL));
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}

	random_shuffle(v.begin(), v.end());
	for_each(v.begin(), v.end(),myPrint2);
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

random_shuffle洗牌算法比较使用，使用时==记得加随机数种子==；

##### 14.3.3 merge

功能：将两个容器合并，并存储到另一个容器中；

`merge(iterator beg1,iterator end1,iterator beg2,iterator end2,iterator dest);`

==//两个容器必须是有序的；==

//dest 目标容器开始迭代器

```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

void myPrint3(int val)
{
	cout << val << " ";
}
void test03()
{
	vector<int>v1;
	vector<int>v2;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
		v2.push_back(i + 1);
	}
	//目标容器
	vector<int>vTarget;
	//提前给目标容器分配空间
	vTarget.resize(v1.size() + v2.size());
	merge(v1.begin(), v1.end(), v2.begin(), v2.end(), vTarget.begin());
	for_each(vTarget.begin(), vTarget.end(), myPrint3);
	cout << endl;
}

int main()
{
	test03();
	system("pause");
	return 0;
}
```

##### 14.3.4 reverse

功能：将容器内元素进行反转；

`reverse(iterator beg,iterator end);`

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

void myPrint4(int val)
{
	cout << val << " ";
}
void test04()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}
	cout << "反转前：" << endl;
	for_each(v.begin(), v.end(), myPrint4);
	cout << endl;
	cout << "反转后：" << endl;
	reverse(v.begin(), v.end());
	for_each(v.begin(), v.end(), myPrint4);
	cout << endl;
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 14.4常用拷贝和替换算法

##### 14.4.1 copy

功能：容器内指定范围的元素拷贝到另一个容器中；

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

void myPrint(int val)
{
	cout << val << " ";
}
void test01()
{
	vector<int>v1;
	vector<int>v2;
	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
	}
	v2.resize(v1.size());
	copy(v1.begin(), v1.end(), v2.begin());
	for_each(v2.begin(), v2.end(), myPrint);
	cout << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 14.4.2 replace

功能：将容器指定范围的旧元素替换成新元素；

`replace(v.begin(),v.end(),val1,val2);`

将容器范围内所有val1替换为val2;

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

class MyPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};
void test02()
{
	vector<int>v;
	v.push_back(10);
	v.push_back(20);
	v.push_back(30);
	v.push_back(40);
	v.push_back(50);
	v.push_back(60);
	v.push_back(10);
	cout << "替换前：" << endl;
	for_each(v.begin(), v.end(), MyPrint());
	cout << endl;

	cout << "替换后：" << endl;
	replace(v.begin(), v.end(), 10, 1000);
	for_each(v.begin(), v.end(), MyPrint());
	cout << endl;
}
int main()
{
	test02();
	system("pause");
	return 0;
}
```

##### 14.4.3 replace_if

`replace_if(iterator beg,iterator end,_Perd,newvalue);`

利用仿函数可以灵活使用筛选条件；

```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
class MyPrint3
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};
class Greater30
{
public:
	bool operator()(int val)
	{
		return val >= 30;
	}
};
void test03()
{
	vector<int>v;
	v.push_back(10);
	v.push_back(20);
	v.push_back(30);
	v.push_back(40);
	v.push_back(50);
	v.push_back(60);
	v.push_back(10);

	cout << "替换前：" << endl;
	for_each(v.begin(), v.end(), MyPrint3());
	cout << endl;

	replace_if(v.begin(), v.end(), Greater30(), 3000);
	cout << "替换后：" << endl;
	for_each(v.begin(), v.end(), MyPrint3());
	cout << endl;
}

int main()
{
	test03();
	system("pause");
	return 0;
}
```

##### 14.4.4 swap

功能：互换同类型容器互换；

```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

class MyPrint4
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};
void test04()
{
	vector<int>v1;
	vector<int>v2;

	for (int i = 0; i < 10; i++)
	{
		v1.push_back(i);
		v2.push_back(i + 100);
	}
	cout << "替换前：" << endl;
	for_each(v1.begin(), v1.end(), MyPrint4());
	cout << endl;

	for_each(v2.begin(), v2.end(), MyPrint4());
	cout << endl;

	cout << "替换后：" << endl;
	swap(v1, v2);
	for_each(v1.begin(), v1.end(), MyPrint4());
	cout << endl;

	for_each(v2.begin(), v2.end(), MyPrint4());
	cout << endl;
	
}

int main()
{
	test04();
	system("pause");
	return 0;
}
```

#### 14.5常用算术生成算法

算术常用算法属于小型算法，头文件为：`#include<numeric>`

##### 14.5.1 accumulate

`accumulate(iterator beg,iterator end,val);`

val为起始值；

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<numeric>

void test01()
{
	vector<int>v;
	for (int i = 0; i <= 100; i++)
	{
		v.push_back(i);
	}

	int sum = accumulate(v.begin(), v.end(),10);
	cout << sum << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

##### 14.5.2 fill

功能：向容器中填充元素

`fill(iterator beg,iterator end,val);`

```c++
#include<iostream>
#include<vector>
using namespace std;
#include<numeric>
#include<algorithm>

void Myprint(int val)
{
	cout << val << " ";
}
void test02()
{
	vector<int>v;
	v.resize(10);

	//后期重新填充
	fill(v.begin(), v.end(), 100);

	for_each(v.begin(), v.end(), Myprint);
}
int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 14.6常用集合算法

##### 14.6.1 set_intersection

功能：求两个容器的交集

`set_intersection(iterator beg1,iterator end1,iterator beg2,iterator end2,iterator dest);`

##### 14.6.2 set_union

功能：求两个容器的并集

`set_union(iterator beg1,iterator end1,iterator beg2,iterator end2,iterator dest);`

##### 14.6.3 set_difference

功能：求两个容器的差集

`set_difference(iterator beg1,iterator end1,iterator beg2,iterator end2,iterator dest);`



