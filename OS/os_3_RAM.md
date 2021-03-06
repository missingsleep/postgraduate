# 内存管理
## 3.0基础知识
### 内存概念
内存是用于存放数据的硬件。程序执行前需要先放到内存中才能被CPU处理。  
每个内存地址对应一个存储单元。
- 按字节编址，每个存储单元大小为1字节。8个二进制位。
- 按字编址，每个存储单元大小位1个字。166个二进制位。

### 内存运行原理
从源程序到可执行程序的步骤：
1. 编译。将源代码编译成若干目标模块。
2. 链接。 链接程序将编译后的模块形成一组目标模块及库函数链接在一起，形成完整的装入模块。
3. 装入。 将装入模块放到内存中运行。  

**装入模块拥有完整的逻辑地址**
#### 装入的三种方式
1. 绝对装入
2. 静态重定位
3. 动态重定位

##### 绝对装入
在编译时，如果知道程序将放到内存中的哪个位置，编译程序将产生绝对地址的目标代。装入程序按照装入模块的地址，将程序和数据装入内存。  
在装入模块中已经是绝对地址了。  
**只适用于单道程序环境**
##### 静态重定位
由装入程序执行。  
在装入程序装入时，对地址进行重定位。根据初始地址变化来让所有地址改变。  
特点：必须分配其要求的全部内存空间。没有足够内存，不能装入该作业。  
##### 动态重定位
装入程序装入时仍然是逻辑地址。地址转换要等到程序真正运行时。  
这种方式需要重定位寄存器。  

#### 链接的三种方式
1. 静态链接
2. 装入时动态链接。在装入内存时边装入边链接。
3. 运行时动态链接。 需要该模块时才进行链接。优点是，便于修改和更新，便于实现对目标模块的共享。  

## 3.1内存管理的相关概念
1. 内存空间的分配与回收
2. 逻辑上对内存空间扩充。
3. 地址转换。（三种装入方式）。
4. 内存保护。各个程序之间互不干扰。

#### 内存保护
方法一：设置一对上，下限寄存器，存放上下限地址。  