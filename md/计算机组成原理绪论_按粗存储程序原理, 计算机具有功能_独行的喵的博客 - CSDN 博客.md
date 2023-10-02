> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_45863060/article/details/121003620)

#### 文章目录

*   [绪论](#_1)
*   *   [一. 计算机硬件的基本组成](#_2)
    *   *   [1. 冯诺依曼计算机的特点](#1_3)
        *   [2. 现代计算机的硬件系统组成](#2_23)
        *   [3.CPU 三大部件的基本组成](#3CPU_28)
        *   *   [1）存储器的基本组成](#1_29)
            *   [2）运算器的基本组成](#2_43)
            *   [3）控制器的基本组成](#3_50)
        *   [4. 指令的组成与执行过程](#4_58)
    *   [二. 计算机软件](#_75)
    *   *   [1. 系统软件与应用软件](#1_76)
        *   [2. 计算机语言](#2_82)

绪论
--

### 一. 计算机硬件的基本组成

#### 1. 冯诺依曼计算机的特点

*   **1. 计算机由五大部件组成：运算器，存储器，控制器，输入设备，输出设备。**
*   **2. 指令和数据以同等地位存于存储器，可按地址寻访。**
*   **3. 指令和数据用二进制表示。**
*   **4. 指令由操作码和地址码组成。**
*   **5. 存储程序。**
*   **6. 以运算器为中心。**

关于存储程序原理：存储程序是指将指令以代码形式事先输入计算机主存储器，然后按其在存储器中的首地址执行程序的第一条指令，以后就按该程序的规定顺序执行其他指令，直至程序执行结束。  
计算机按照此原理应该具有五大功能：数据传送功能，数据存储功能，数据处理功能，操作控制功能，操作判断功能。  
![](https://img-blog.csdnimg.cn/3ab98c334bbb47ca9f253f5fcba6fe58.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)实线：表示数据通路  
虚线：表示控制和状态反馈

冯诺依曼计算机体系的缺点：以运算器为中心的结构使得运算器过于繁忙，运算器的性能成为了计算机系统性能的瓶颈。

基于冯诺依曼计算机硬件结构的改进：将以运算器为中心的结构改变为以存储器为中心的结构：输入设备输入的数据直接进入到存储器当中，并且存储器的数据可直接从输出设备输出而不用经过运算器，减轻了运算器的负担。  
![](https://img-blog.csdnimg.cn/a446145d18ea4c36b6c848cddda8931d.png)

#### 2. 现代计算机的硬件系统组成

![](https://img-blog.csdnimg.cn/0e8dc99d837b4032aaf8ce31d96fd246.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)  
主存即内存，辅存即外存（硬盘）

#### 3.CPU 三大部件的基本组成

##### 1）存储器的基本组成

*   存储体：存储体由**存储单元**构成，存储单元由多个存储元件构成。存储单元存放由指令和数据构成的二进制代码。
    
*   MAR：**存储器地址寄存器**，保存存储单元的地址或编号。（Memory Address Register）MAR 的位数 n 与存储单元个数 m 的关系：  
    2 n = m 2^n=m 2n=m
    
*   MDR：**存储器数据寄存器**，保存了要将存到 cpu 中的数据或将要存到存储体中的数据。（Memory Data Register）MDR 的位数与存储字长相等
    

![](https://img-blog.csdnimg.cn/a108dd2f027d45199a12719dbd680414.png#pic_center)  
  
**存储单元：存储体由很多个存储单元构成，每一个存储单元存放一串二进制数**  
**存储字：每一个存储单元中保存中的数据，即一串二进制数。**  
**存储字长：存储字的长度，即存放的一串二进制数的位数。**

##### 2）运算器的基本组成

*   ACC: 累加器
*   ALU：算术逻辑运算单元
*   MQ：乘商寄存器
*   X：操作数寄存器  
    ![](https://img-blog.csdnimg.cn/6cf07a7771cc4e7d9e4db2ed1558439e.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)

##### 3）控制器的基本组成

*   **程序计数器 PC**：用来存放当前欲执行指令的地址，可以自动加 1 以形成下一条指令的地址，它与主存的 MAR 之间有一条直接通路。
*   **指令寄存器 IR**：用来存放当前的指令，其内容来自主存的 MDR。指令中的操作码 OP 送至 CU，用以分析指令并发出各种微操作命令序列；而地址码 Ad 送往 MAR，用以取操作数。
*   **控制单元 CU**：分析指令并发出各种微操作命令序列。形成对指令执行的控制信号。

#### 4. 指令的组成与执行过程

指令由操作码和地址码组成，  
一条指令是长度为 16 位的[二进制](https://so.csdn.net/so/search?q=%E4%BA%8C%E8%BF%9B%E5%88%B6&spm=1001.2101.3001.7020)数  
其中 操作码的长度为 6 位，地址码的长度为 10 位

![](https://img-blog.csdnimg.cn/6937897ea26c4f48810ba35360b5bf65.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_14,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/7634097eddab4481a3945cfee156a059.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_14,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/4dc197607b5e4be5972d1f0e778b51c6.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_14,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/9de35509d1a743a5ae5d0559df958570.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_14,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/dd36e6e7f50349c1a647cf0521b8c8f0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_15,color_FFFFFF,t_70,g_se,x_16)  
![](https://img-blog.csdnimg.cn/d759d0b6780a419680575f8f874a3ac3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_15,color_FFFFFF,t_70,g_se,x_16)  
![](https://img-blog.csdnimg.cn/58f8c482745e4ee897da542c0e5878b3.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA54us6KGM55qE5Za1,size_16,color_FFFFFF,t_70,g_se,x_16)

### 二. 计算机软件

#### 1. 系统软件与应用软件

计算机软件按功能分类可分为系统软件和应用软件  
系统软件：系统软件是一组保证计算机高效，正确运行的基础软件，通常作为系统资源提供给用户使用。系统软件主要有：**操作系统（OS），数据库管理系统（DBMS），语言处理程序，分布式系统软件，网络软件系统，标准库程序，服务性程序**等。

注：数据库管理系统是系统软件，但数据库系统不是系统软件，数据库系统包括：数据库，数据库管理系统，应用系统，数据库管理员。

#### 2. 计算机语言

计算机语言分为三个级别：机器语言，汇编语言，高级语言

*   机器语言：计算机唯一可以直接识别和执行的语言
*   汇编语言：使用英文单词或缩写（助记符）代替二级制的指令代码
*   高级语言：方便程序设计人员使用的，面向自然语言的语言。需要通过编译程序编译成汇编语言程序，然后经汇编得到机器语言程序。

由于计算机无法直接理解和执行高级语言程序，需要通过翻译程序进行转换：

*   汇编程序：将汇编语言程序翻译成机器语言程序
*   解释程序：将源程序中的语句按执行顺序逐条翻译成机器指令并立即执行，由于解释程序是便翻译边执行的程序，所以执行速度较慢
*   编译程序：将高级语言程序翻译成汇编语言或机器语言程序，编译程序会生成目标代码文件，而解释程序不会生成目标代码文件。