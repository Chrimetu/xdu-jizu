> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_45863060/article/details/127260710)

#### 文章目录

*   [CISC 与 RISC](#CISCRISC_2)
*   *   [1.CISC](#1CISC_5)
    *   [2.RISC](#2RISC_25)

CISC 与 RISC
-----------

### 1.CISC

**CISC：Complex Instruction Set Computer，复杂指令集计算机**

CISC 结构计算机的设计目标是通过强大的指令系统来支持系统实现强大的功能。  
该结构支持的指令系统的指令数量通常在几百至上千条，寻址方式需要用 1~2 个字节来表示，指令长度可以达到十几个字节。这个复杂庞大的指令系统需要许多硬件功能部件的支持才能得以实现，所以 CISC 系统的硬件结构通常也相当复杂。

**早期 CISC 设计有如下特点；**

*   （1）指令系统复杂，指令数量多，寻址方式多，指令格式多。
*   （2）绝大多数指令执行需要多个时钟周期。
*   （3）有多种指令可以访问存储器。
*   （4）CPU 控制器采用微程序控制方式实现。
*   （5）寄存器数量有限。

**CISC 指令集计算机的弊端：**

*   （1）CPU 控制器很复杂，相应的主存储器必须有更大的空间，这会增加指令执行的时间，抵消复杂指令预期带来的速度优势。
*   （2）繁多的指令会使计算机研制周期变长，调试和维护难度大。
*   （3）复杂指令系统必然增加硬件设计和制造的复杂新，增加了研制成本。

### 2.RISC

**RISC：Reduced Instruction Set Computer，精简指令集计算机**

**基于 RISC 结构的指令集系统都遵从 RISC 思想：**

*   （1）指令字定长
*   （2）使用 load/store 指令
*   （3）寻址方式有限
*   （4）指令数量有限

**RISC 结构的计算机具有如下特点：**

*   （1）只设置使用频度高的简单指令，所以指令的操作种类少，寻址方式少
*   （2）指令格式规范，长度固定，便于简单同一译码，可使控制器简化，硬件结构精简。
*   （3）仅通过 Load 和 Store 指令访问主存。
*   （4）通用寄存器数量多，一般有几十甚至几百个，大多数操作在寄存器之间进行。
*   （5）在非流水线 RISC 中，单条指令可在单个机器周期内完成；在流水线 RISC 中，对于大多数指令有 CPI=1.
*   （6）采用硬布线控制器，不使用微程序，有利于提高时钟频率和 CPU 速度，能够更好地响应中断。

**RISC 指令集的优势：**

*   （1）可简化硬件设计，降低成本，便于超大规模集成电路实现
*   （2）有利于多流水线，多核 CPU 实现
*   （3）适宜高度优化编译器（即编译程序）

**RISC 指令集的缺陷：**

*   （1）精简的指令使程序阅读，分析难度加大。
*   （2）不能同 CISC 兼容。解决方法：一是将源程序在 CISC 机器上重新编译；二是用目标代码翻译器将 CISC 代码翻译成 RISC 代码。