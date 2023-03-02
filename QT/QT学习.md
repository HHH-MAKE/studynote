

# QT

## 1.注意事项

1. 项目名称和路径不能有中文和空格



## 2.第一个QT程序

mywidget.h

```c++
#ifndef MYWIDGET_H
#define MYWIDGET_H

#include <QWidget>

class myWidget : public QWidget
{
    Q_OBJECT

public:
    myWidget(QWidget *parent = nullptr);
    ~myWidget();
};
#endif // MYWIDGET_H

```

mywidget.cpp

```c++
#include "mywidget.h"

//命名规范
//类名：首字母大写，单词和单词之间首字母大写
//函数名 变量名称 首字母小写，单词和单词之间首字母大写

//快捷键
//注释 ctrl + /
//运行 ctrl + r
//编译 ctrl + b
//字体缩放 ctrl + 鼠标滚轮
//查找 ctrl + f
//整行移动 ctrl + shift + ↑ 或 ↓
//自动对齐 ctrl + i
//同名.h和.cpp文件切换 F4

myWidget::myWidget(QWidget *parent)
    : QWidget(parent)
{
}

myWidget::~myWidget()
{
}
```

main.cpp

```c++
#include "mywidget.h"

#include <QApplication>//包含一个应用程序类的头文件

//argc,命令行变量的数量；argv命令行变量的数组

int main(int argc, char *argv[])
{
    //a为应用程序对象，在QT中，应用程序对象有且仅有一个
    QApplication a(argc, argv);
    //窗口对象 mywidget父类->QWidget
    myWidget w;
    //窗口对象，默认不会显示，需要调用show方法显示窗口
    w.show();
    //让应用程序对象进入消息循环,使窗口一直存在
    //让代码阻塞到这一行
    return a.exec(); 
}
```

project01.pro

```c++
QT       += core gui//QT包含的模块 core核心模块 gui图形模块

greaterThan(QT_MAJOR_VERSION, 4): QT += widgets//大于4版本以上，包含widget模块

CONFIG += c++11

# The following define makes your compiler emit warnings if you use
# any Qt feature that has been marked deprecated (the exact warnings
# depend on your compiler). Please consult the documentation of the
# deprecated API in order to know how to port your code away from it.
DEFINES += QT_DEPRECATED_WARNINGS

# You can also make your code fail to compile if it uses deprecated APIs.
# In order to do so, uncomment the following line.
# You can also select to disable deprecated APIs only up to a certain version of Qt.
#DEFINES += QT_DISABLE_DEPRECATED_BEFORE=0x060000    # disables all the APIs deprecated before Qt 6.0.0

SOURCES += \				//源文件
    main.cpp \
    mywidget.cpp

HEADERS += \				//头文件
    mywidget.h

TRANSLATIONS += \			//翻译文件
    project01_zh_CN.ts

# Default rules for deployment.
qnx: target.path = /tmp/$${TARGET}/bin
else: unix:!android: target.path = /opt/$${TARGET}/bin
!isEmpty(target.path): INSTALLS += target

```

## 3.QPushButton创建

创建按钮：`QPushButton *btn = new QPushButton`

设置父亲：`setParent(this)`

设置窗口大小：`setSize(长，宽)`

设置固定窗口大小：`setFixedSize(长，宽)`

设置窗口标题：`setWindowTitle()`

```c++
#include "mywidget.h"
#include<QPushButton>//按钮控件的头文件

myWidget::myWidget(QWidget *parent)
    : QWidget(parent)
{
    //创建一个按钮
    QPushButton * btn = new QPushButton;

    //btn->show();//show默认是显示在顶层弹出单独窗口

    //让btn对象显示在创建的窗口中
    btn->setParent(this);

    //显示文本
    btn->setText("第一个按钮");

    //创建第二个按钮
    //创建按钮跟快捷
    //按照控件大小创建按钮
    QPushButton * btn2=new QPushButton("第二个按钮",this);

    //移动btn2按钮
    btn2->move(100,100);

    //重置窗口大小
    resize(600,400);

    //设置固定窗口大小
    setFixedSize(600,400);

    //设置窗口标题
    setWindowTitle("第一个窗口");
}

myWidget::~myWidget()
{
}
```

## 4.对象模型(对象树)

不用管理释放的操作，将对象会放入到对象中；一定程度上简化了内存回收机制。

新增一个自己的按钮类myPushButton

myPushButton.h，public继承QWidget需要修改为QPushButton

```c++
#ifndef MYPUSHBUTTON_H
#define MYPUSHBUTTON_H

#include <QWidget>
#include<QPushButton>

class myPushButton : public QPushButton
{
    Q_OBJECT
public:
    explicit myPushButton(QWidget *parent = nullptr);

    ~myPushButton();
signals:

};

#endif // MYPUSHBUTTON_H
```

myPushButton.cpp

```c++
#include "mypushbutton.h"
#include<QDebug>
myPushButton::myPushButton(QWidget *parent) : QPushButton(parent)
{
    qDebug()<<"我的按钮类调用";
}

myPushButton::~myPushButton()
{
    qDebug()<<"我的按钮类析构";
}
```

mywidget.cpp

```c++
    //创建一个自己的按钮对象
    myPushButton * myBtn =new myPushButton;
    myBtn->setParent(this);
    myBtn->setText("我自己的按钮");
    myBtn->move(200,100);
```

## 5.QT窗口坐标系

以左上角为原点(0,0);x轴以右为正方向，y轴以下为正方向；

## 6.信号signals和槽slots

`connect(信号的发送者，发送的具体信号，信号的接收者，信号的处理(槽));`

信号槽的优点：信号的发送方和信号的接收方是松散耦合的，发送端和接收端本身没有关联的，通过connect连接 将两端耦合在一起；

```c++
 //需求 点击我的按钮，关闭窗口
 //参数1 信号的发送者 参数2 发送的信号
 //参数3 信号的接收者 参数4 处理的槽函数
    connect(myBtn,&myPushButton::clicked,this,&myWidget::close);
    //connect(myBtn,&QPushButton::clicked,this,&QWidget::close);两行效果一样
```

## 7.自定义信号和槽

signals:

- 自定义信号写到signals下面
- 返回值是void，只需要声明，不需要实现
- 可以有参数，可以重载

public slots:

- 槽函数可以写到这下面
- 也可以之间写到public下面
- 或者写全局函数也可以
- 返回值为void，需要声明，也需要实现
- 也可以有参数，可以重载

emit自定义信号；

teacher.h

```c++
#ifndef TEACHER_H
#define TEACHER_H

#include <QObject>

class Teacher : public QObject
{
    Q_OBJECT
public:
    explicit Teacher(QObject *parent = nullptr);

signals:
    //自定义信号写到signals下面
    //返回值是void，只需要声明，不需要实现
    //可以有参数，可以重载
    void hungry();//无参
};

#endif // TEACHER_H
```

student.h

```c++
#ifndef STUDEMT_H
#define STUDEMT_H

#include <QObject>

class Student : public QObject
{
    Q_OBJECT
public:
    explicit Student(QObject *parent = nullptr);

signals:

public slots:
    //槽函数可以写到这下面
    //也可以之间写到public下面
    //或者写全局函数也可以
    //返回值为void，需要声明，也需要实现
    //也可以有参数，可以重载
    void treat();
};

#endif // STUDENT_H
```

myWidget.cpp

```c++
#include "mywidget.h"
#include "ui_mywidget.h"

//Teacher类 老师类
//Student类 学生类
//下课后，老师会触发信号：饿了，学生响应信号，执行槽函数：请客

MyWidget::MyWidget(QWidget *parent)
    : QWidget(parent)
    , ui(new Ui::MyWidget)
{
    ui->setupUi(this);

    //创建一个老师对象
    this->ls=new Teacher(this);

    //创建一个学生对象
    this->xs=new Student(this);

    connect(ls,&Teacher::hungry,xs,&Student::treat);

    //调用下课函数
    classIsOver();
}

 void MyWidget::classIsOver()
 {
     //下课函数
     emit ls->hungry();
 }

MyWidget::~MyWidget()
{
    delete ui;
}
```

## 8.自定义信号槽的重载处理

自定义信号和槽出现重载，需要利用函数指针，明确指向函数的地址；

```c++
	void hungry(QString foodname);//有参
```

```c++
    void Student::treat(QString foodname)
    {
        qDebug()<<"请老师吃饭，老师要吃"<<foodname.toUtf8().data();
    }
```

```c++
 	//connect(ls,&Teacher::hungry,xs,&Student::treat);无参
    //信号重载的时候需要区分
    //函数指针->函数地址
    void(Teacher::*teacherSignal)(QString)=&Teacher::hungry;
    void(Student::*studentSlot)(QString)=&Student::treat;
    connect(ls,teacherSignal,xs,studentSlot);
    //调用下课函数
    classIsOver();
```

## 9.信号连接信号

信号1触发->信号2触发->信号3触发

```c++
    //点击下课按钮触发下课
    QPushButton * btn= new QPushButton("下课",this);
    this->resize(600,400);
    //点击按钮触发下课
    		       //connect(btn,&QPushButton::click,this,&MyWidget::classIsOver);

    //无参信号和槽链接
    void(Teacher::*teacherSignal2)(void)=&Teacher::hungry;
    void(Student::*studentSlot2)(void)=&Student::treat;
    connect(ls,teacherSignal2,xs,studentSlot2);
    //信号链接信号
    connect(btn,&QPushButton::clicked,ls,teacherSignal2);
	//断开信号
    disconnect(ls,teacherSignal2,xs,studentSlot2);

    //拓展
    //信号可以链接信号
    //一个信号可以连接多个槽函数
    //多个信号可以链接同一个槽函数
    //信号和槽的参数类型要一致
    //信号的参数个数可以多于槽的参数个数，但是类型也要保持一致

    //qt4版本以前的信号槽连接
    //利用qt4的信号槽连接
    //qt4优点：直观，缺点：类型不做检测
    connect(ls,SIGNAL(hungry()),xs,SLOT(treat()));
```

## 10.Lambda表达式

qt老版本需要在.pro文件中加入  `CONFIG +=C++11`

lambda表达式用于定义并创建匿名的函数对象；

```c++
[capture](parameters)mutable->return-type
{
	statemen
}
```

[]是标识一个Lambda的开始，这部分必须存在，不能省略；

[]里面可以有参数：

- 空，没有使用任何函数对象参数
- =，可以使用lambda所在作用范围内所有可见的局部变量，并且采用==值传递方式；==
