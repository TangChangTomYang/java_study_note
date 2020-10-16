#   aeclipse 快捷键

- eclipse 中 导 包 的快捷键`ctrl + shift + o` , 也可以用`ctrl + 1` 来修复

  即, 当java文件中因为没有导入文件报错时, 直接`ctrl + shift + o`  来修复

- eclipse 中自动生成`get` 、`set` 、`constructor`、`toString` 常用代码的快捷键: `shift + Alt + s`

  Mac 中为 `option + command + s`

  





# 一、初识java+搭建开发环境

## 1、java介绍

java是全世界最流行的开发语言之一, 长期霸占TIOBE编程热门语言排行榜前3名

java最初由就职用于SUN公司的James Gosling 等人发明. SUN公司全称: Sun Microsystems, 其中SUN 是Stanford University Network的缩写(斯坦福大学网络)

SUN 公司在2009年被Oracle (甲骨文) 公司以74亿美金收购

java有3大版本: java SE, java ME , java EE(以前也分别叫做: j2SE, j2ME, j2EE)

- java SE (java platform, Standard Edition, java 平台标准版)
  - 是javaME, JavaEE的编程基础, 可以用来开发一些桌面应用, 游戏
- javaME(java platform, micro Edition, java平台微信版)
  - 主要应用在移动设备和嵌入式设备(比如: 手机,pad, 电视机顶盒等) , 以前一些智能手机(诺基亚等)上的应用, 游戏就是基于javvaME 开发的. 
- javaEE(java platform, Enterprise Edition, java 平台企业版) 
  - 主要用于企业级应用(后台管理系统等) 
  - java3大版本中,市场需求最大的就是javaEE, 很多人学习java, 最终从事的就是javaEE开发

## 2、java的版本演进

一般我们说的java的版本, 指的就是javaSE 的版本, JDK版本

![](images/Snip20200922_2.png) 



## 3、java开发必备

想要顺利开发java程序, 有2个必须要安装的软件: JDK、JRE

- JDK (java Development kit), java开发工具包
  - 提供了开发中要用到的各种常用工具
- JRE( java Runtime Environment), java 运行环境
  - 将开发完的java程序运行到JVM上

> 一般我们是这样一个流程
>
> **使用JDK开发一套java程序, 利用JRE将程序运行到JVM上** 

![](images/Snip20200922_3.png) 

**从上图可以看出, JDK中已经包含了 JRE, JRE中已经包含了JVM, 所以我们开发中只需要安装JDK就可以了. ** 



## 4、JDK 的下载

JDK中已经包含了JRE, 所以不需要单独下载JRE, 只下载JDK即可

下载地址: https://www.oracle.com/technetwork/java/javase/downloads/index.html





# 二、java的数据类型

## 1、Java数据类型介绍

java的数据类型就两大类:

- **基本数据类型(primitive type)** 
  - **byte**: 8-bit的整数, 取值范围 [128, 127]
  - **short**: 16-bit的整数, 取值范围[-32768, 32767]
  - **int**: 32-bit的整数
  - **long**: 64-bit的整数
  - **float**: 单精度32bit 浮点数
  - **double**: 双精度64bit浮点数
  - **boolean**: 布尔类型, 只有true 和 false
  - **char**: 单个 16-bit的unicode字符, (即一个char相当于是16bit的整数)
- **引用数据类型(reference type)**



## 2、字面量 (Literal)

- 整数

  ```
  // 十进制
  byte v1 = 123;
  
  // 二进制 (或0B11001)
  short v2 = 0b11001;
  
  //十六进制(或者 0xF78A, 0xf78a)
  int v3 = 0XF78A;
  
  // 以L或者l 结尾表示long类型(或者 199l)
  long v4 = 199L;
  ```

- 浮点数

  ```
  // 以F或者f结尾表示浮点数 float类F(或者 123.4f)
  float v1 = 123.4F;
  
  // 以D或者d结尾表示 double 类型(或者 123.4d)
  double v2 = 123.4D;
  
  // 默认是double 数据类型
  double v3 = 123.4;
  
  // 可以使用科学计数(E 或者 e)
  float v4 = 1.234E2f;
  double v5 = 1.234e2
  ```

  > 注意:
  >
  > 在java中, 浮点数默认就是 double 类型, 如下:
  >
  > double d1 = 1.34;  等价于 double d2 = 1.34d;
  >
  > 如果想用字面量表示一个float, 那么必须写成 `1.34f`   数字后面要有 `f` , 或者 (float)1.34;

- 字符和字符串

  ```
  // 使用单引号表示字符
  char c1 = 'A';
  
  // 使用双引号表示字符串
  String s1 = "abc";		// String 在java中属于引用数据类型
  ```

- 布尔

  ```
  boolean v1 = true;
  boolean v2 = false;
  ```

- 空值

  ```
  String v1 = null;
  
  注意: 在java中, 空值不等于空字符串, 空值null 表示不指向任何对象
  ```



## 3、在数字中使用下划线

从java7开始, 可以给数字添加下划线增强可读性

```
int v1 = 1_0000_0000;
int v2 = 0xFF_EC_DE_5E;
int v3 = 0b1100_0011;
double v4 = 12.23_23_23;
long v5 = 1__0000_000;		// 多个下划线也可以连在一起写

```

下面的写法是错误的

```
//  不能在浮点数的小数点前后写下划线 _
double d1 = 1._23;
double d2 = 1_.23;

// 不能在数字的前后写下划线 _
int  v1 = _123;
int v2 = 223_;

// 不能在X B F D L E 等特殊字母的前后使用下划线
byte v3 = 0x_12;
byte v4 = 0_b1002;
float v5 = 1.12_f;
long v6 = 189_L;
```



## 4、变量的初始化

任何变量在使用前都必须初始化(赋值)

- **局部变量, 需要程序员手动初始化** 

  ```
  void test(){
  	// int age;
  	// System.out.println(age); // 错误,变量在使用前必须初始化
  	
  	// 下面是正确做法
  	int age = 18;
  	System.out.println(age);
  	
  	// 也可以这样
  	double height;
  	height = 1.88;
  	System.out.println(height);
  }
  ```

  

- **非局部变量(实例变量, 类变量)** 

  **编译期会自动给未初始化的变量设置一个初始值** , 程序员可以不用管, 自动有初始值

  ```
  public class Main{
  	// 像这种, 成员变量, 实例变量编译器会自动帮我们初始化
  	private int age;
  	private static double height; // 类变量, 编译器也会帮助我们初始化
  	
  	public static void main(String[] args){
  		int count; // 局部变量, 在使用前必须初始化
  		System.out.println(count); // 错误, count在使用前必须初始化
  	}
  	
  }
  ```

- **编译器默认的初始值** 

  | 数据类型       | 默认初始值 |
  | -------------- | ---------- |
  | byte           | 0          |
  | short          | 0          |
  | int            | 0          |
  | long           | 0          |
  | float          | 0.0f       |
  | double         | 0.0d       |
  | char           | '\u0000'   |
  | boolean        | false      |
  | 对象(引用类型) | null       |

  



## 5、运算符(注意点)

![](images/Snip20200923_5.png) 



### 1、表达式 (注意点) 容易犯错

**java中的算术表达式的结果 必须被使用, 否则报错** 

> 但是在其它语言里没有这个特点, 这一点需要注意一下, 否则在开发中容易犯错误

```
// 错误写法: 
void test() {
  /// 下面的表达式结果必须被用起来, 否则报错
  10 + 20;
}
	
// 正确做法1 
void test() {
  int sum = 10 + 20;
}

// 正确做法1 
void test() {
  int sum = 10 + 20;
}
// 正确做法2
void test() {
  System.out.println(10 + 20);
}

void test(){
	int[] arr = {1,2,3,4};
	// arr[2]; 错误写法, 表达式必须用起来
	int rst = arr[2];
}
```

> 即, java 中的算术表达式必须被使用



### 2、字符串拼接

java中字符串 使用 `+` 拼接

```
int age = 18;
String name = "zhangsan";
double height = 1.88;
System.out.println(
	"my name is" + name
	+ ", my age is" + age
	+ ", my height is" + height
);
```



### 3、位运算符

- `>>` 与 `>>>` 

  - `>>` 有符号右移动, 左边用符号位补齐

  - `>>>` 无符号右移, 左边用0补齐

    ![](images/Snip20200923_6.png) 

补充:

```
int a = 10; 
/// 将一个整数, 转换成二进制的字符串
System.out.println(Integer.toBinaryString(a));	// 1010
System.out.println(Integer.toHexString(a));		// a		 
```



- `&` , `|` , `^`  按位与, 按位或, 按位异或

  > & 按位与, 相同取1, 不同取0
  > | 按位或, 有1取1, 全0取0
  > ^ 按位异或, 不同取1, 相同取0

  ```
  int age1 = 0b10010;
  int age2 = 0b11111;
  System.out.println(Integer.toBinaryString(age1 & age2)); // 10010
  System.out.println(Integer.toBinaryString(age1 | age2)); // 11111
  System.out.println(Integer.toBinaryString(age1 ^ age2)); // 01101
  ```

  > 在java中, & | ^ 按位与, 按位或, 按位异或除了可以用在整数上, 也可以用在 布尔类型 boolean 类型上

  ```
  System.out.println(false & true);		// false
  System.out.println(false | true);   // true
  System.out.println(false ^ true);		// true
  ```

**说明**

虽然, `&` , `|`, `^` 能用在 boolean 类型的数据上, 且 `&` 与 `&&`  `|` 与`||` 表面上看效果差不多, 

但是, 在实际开发中 `&&` 与 `&`  以及 `||` 与 `|` 还是有区别的, 具体区别如下:

- `&&` 称为短路与, `||` 称为短路或, 而`&` 与`|` 是没有短路功能的, 这一点需要注意一下.



## 6、(重点)类型转换(type conversion)

### 1、拓宽基本类型转换(Widening Primitive Conversion)

所谓拓宽基本数据类型就是将 **数据范围小的转换为数据范围大的** (19种), 可以自动转换**(隐士转换)** 

- byte 转 short, int, long, float, double

- short 转 int, long, float, double

- int 转 long, float, double

- long 转 float, double

- float 转 double

- char 转 int, long, float, double

  ```
  byte b = 12;
  short s = b;
  int i1= s;
  
  char c = 'A';
  int i2 = c;
  
  long L1 =i1;
  float f = L1;
  double d = f;
  ```

### 2、窄化基本类型转换(Narrowing Primitive Conversion)

所谓窄化基本数据类型转换, 就是将数据范围大的转化为数据范围小的(22种), 可能会丢失精度和范围, **需要强制转换** 

- short 转 byte, char
- char 转 byte, short
- int 转 byte, short, char
- long 转 byte, short, char, int
- float 转 byte, short, chart, int, long
- double 转 byte, short, char, int, long, float

```
short s = 512;
char c = (char)s;
byte b = (byte)c;

double d = 12.3;
float f = (float)d;
int i = (int)d;
```

> 注意:
>
> 布尔类型和整型浮点型之间是不能互相转换的, 这个在java开发



### 3、一元数字提升(Unary Numeric Promotion)

**一元数字提升:
将`byte`, `short`, `char` 类型的一元数字自动提升为`int`类型(拓宽基本数据类型转换)**  

> 所谓的一元运算符就是操作一个数字的运算符,常见的一元数字提升运算符有:
>
> 数组的方括号运算符[], 正号 + , 负号 -, 按位取反 ~  , 位移运算符 >> << >>> 
>
> 注意: ++ 和 -- 不是一元运算提升符号

说白了, 所谓的一元数字提升就是说当我们使用一元运算符操作一个数字(byte, short, char) 时, 编译器会自动的将这个数字(byte, short, char) 提升为 int 的数据类型, 换句话说一元数字提升就相当于是编译器自动帮助我们执行了 (int)byte, int(short), (int)char 的操作, 示例如下: 

- 示例说明1

  ```
  byte index = 1;
  int[] arr = [1,2,3,4];
  
  int rst = int[index]; // 此处 index 经过 [] 一元运算符处理后, 结果自动转换为 int 类型的了
  
  换句话说, 与下面这两句等价
  int a = 1;
  int rst = int[a]; // 相当于int rst = int[(int)a];的感觉
  ```

- 示例说明2

  ```
  byte b1 = 10;
  byte b2 = -b1; // 这句报错, -b1 的结果是int类型, 不能直接赋值给 byte 需要手动强制转换
  byte b3 = +b1; // 这句报错, +b1 的结果是int类型, 不能直接赋值给 byte 需要手动强制转换
  
  // 此处的+是正数的意思, - 是负数的意思
  ```

- 示例说明3

  ```
  char c = 'A';		// 字符在内存中存储的是ASCII值
  System.out.println(c);	// 是char 类型, 打印为 A
  
  System.out.println(+c); // 此处是 int 类型, 打印为 65
  System.out.println(-c); // 此处是 int 类型, 打印为 -65
  ```
  
  > 这也是我们如何将一个字符转换为数字, 或者如何获取一个字符的ASCII 码值常用的方法(使用一元数字提升即可)
  >
  > 相当于System.out.println((int)c); 的感觉

-  示例说明4

  ```
  char c1 = 'A';
  char c2 = +c1; // 错误, 编译不通过
  char c3 = 65;  // 这一句为什么能编译通过呢? 因为字面量 65 的数据类型是不确定了, 可以是byte, short, char, 所以能通过
  
  float height = 1.88; // 错误, 编译不通过, 因为 1.88 默认是double 类型, 不能直接将一个double 类型的数据直接赋值给float类型的数据
  ```

  > 结论: 
  >
  > - 整数字面量比如: 123 的具体类型是不确定的可以是直接赋值给 byte, short, char, 也可以赋值给long编译器会自动将整数字面量123拓宽为long, 等价于 123L
  > - 浮点数 12.3 默认是双精度的类型, 即字面量 12.3 与 12.3L 是一个意思, 因此不能直接将 12.3 赋值给float



### 4 二元数字提升(Binary Numeric Primitive)

二元数字提升这个注意事项如果没掌握的话, 也是让初学java的人员有时对计算结果一头雾水的原因, 为什么报错, 一脸懵逼~~~

我们在学java的时候, 必须要对二元数字提升要有认识, 否则程序报错了就很尴尬



**二元数字提升:**

**提升一个或两个数字(拓宽基本数据类型转换)** 

- 如果任意一个数字是`double` 类型, 那么另外一个就会被转换为`double` 类型,
- 否则, 如果一个数字是`float` 类型, 那么另外一个就会被转换为`float` 类型
- 否则, 如果一个数字是`long` 类型, 那么另外一个就会被转换为`long` 类型
- 否则, 两个数字都被转换为 `int` 类型. 

> 说白了, 就是两个数字在进行运算时, 会先检查有没有double, 如果有就将另外一个不是double的自动转换为double, 这样就相当于 double 与 double 运算, 结果为double, 如果没有double就看有没有是float类型的, 有就将另外一个不是float的转换为float, 再运算
>
> 以此类推,直至int类型
>
> 如果两个数字在运行时, 都不是 double, float, long, int, 那么在运算前全部转换为int类型再运算, 结果为int.

**即, 两个数字在运行时, 结果至少是int 级别的** 

- 常见的二元运算符有:

  > 乘 *, 除 /, 取余 %, 加法 + , 减法 -
  >
  > 比较 < , <=, >, >=
  >
  > 判等 ==, !=
  >
  > 位运算 &, |, ^
  >
  > 三目 ? :

- 示例: (此处我们举一个常见错误例子)

  ```
  byte b3 = b1 + b2;  
  // 错误, 二元数字提升, 最低的数据类型都是 int, 
  // 此处 b1 + b2 相当于 (int)b1 + (int)b2 结果是一个int, int 的结果不能直接赋值给 byte
  		
  // 这样做仍然是错误的做法	
  byte b3 = (byte)b1 + (byte)b2;  
  
  // 正确的做法: 将计算结果强转为 byte 才可以
  byte b3 = (byte)(b1 + b2);  
  
  有个特例
  byte b = 1 + 2; 编译通过, 正确的
  byte b4 = 6;
  b4 += 3; 编译通过, 所以在java开发中你会经常看见+=, -+ , *= 这种操作
  
  ```

  

## 7、标识符

- 标识符: 变量名, 方法名, 类名等, 命名规则如下:

  - 不限长度的 `java字母` , `java数字` 序列, 但必须以`java字母` 开头, 区分大小写

  - 不能使用关键字
  - 不能使用字面量 true, false, null



# 三、数组



## 1、数组的创建

> Java的数组属于引用类型
>
> - 数组元素存储在对空间(heap) 

```
int[] arr1;
int[] arr2 = {}; // 空数组 (推荐这种语法)
int arr3[] = {}; // 空数组 (不推荐这种语法)

// 定义的时候指定数组元素
int[] arr4 = new int[]{1,2,3,4};
int[] arr5 = {1,2,3,4}; // 这个是语法糖

// 定义的时候指定数组长度
int[] arr6 = new int[4];
arr6[0] = 1;
arr6[1] = 1;
arr6[2] = 1;
arr6[3] = 1;

// 多维数组
int[][][] arr7;
int[] arr8[][];
```

> 注意:
>
> 在java中, 字符数组 != 字符串 (C 语言中是等价的)
>
> 字符数组: char[]
>
> 字符串: String



## 2、数组遍历

- 遍历

  ```
  int[] arr = {1,2,3};
  
  for(int i=0; i<arr.length; i++){
  	System.out.println(arr[i]);
  }
  
  // 相当于iOS中的for in
  for(int ele : arr){
  	System.out.println(ele);
  }
  ```

- java数组元素存储在堆空间(heap)

- java的堆内存申请会自动进行初始化

  ```
  int[] arr = new int[4];
  for(int ele : arr) {
  	System.out.println(ele); // 打印 4个 0
  }
  
  String[] arr = new String[4];
  for(String ele : arr) {
  	System.out.println(ele);	// 打印4个null
  }
  ```

## 3、数组的打印

```
String[] arr = new String[4]; 
System.out.println(arr);
```

> 数组的打印如下:
>
> [Ljava.lang.String;@6d06d69c
>
> `Ljava.lang.String; ` 部分 代表的是数组的类型, String 类型
>
> `@6d06d69c`  代表的是数组的 哈希code, 只不过使用十六进制显示的



## 4、可变参数

```
public static int sum(int... nums){
	int rst = 0;
	for(int i=0; i<nums.length; i++){
		rst += nums[i];
	}
	return rst;
}
```

- 可变参数必须是方法的最后一个参数, 否则有歧义会将报错. 

> java JDK中自带的 `System.out.printf()` 方法就是使用了可变参数
>
> 格式字符串参考API文档的 `java.util.Formatter` 类



## 5、参数传递

java中的数据类型2种:

- 基本数据类型:  byte  char short int long float double boolean

  > 值传递

- 引用数据类型: 数组, 对象





# 四、方法



## 1、方法定义

java中的方法就是其他语言中的函数

- 方法的书写格式

  ```
  修饰符 返回值类型 方法名(参数列表){
  	方法体
  }
  ```

- 可变参数

  > 可变参数至少都是一个{}, 不会为null

  ```
  public static int sum(int... nums){
  	int rst = 0;
  	for(int i=0; i<nums.length; i++){
  		rst += nums[i];
  	}
  	return rst;
  }
  
  
  // 外面使用
  sum();// 可以
  sum(1,2,3,4,5); // 也可以, 这就是可变参数
  ```

  > 注意:
  >
  > 方法中的可变参数, 必须是方法的最后一个参数



## 2、方法签名(Method Signature)



- 方法签名由两部分组成: `方法名` 和 `参数类型` 

  > 注意: 方法签名不包含返回值

- 下面的方法签名是: `sum(int, long, double)`

  ```
  public static double sum(int i, long l, double d){
  	return i + l + d;
  }
  ```

- 同一个类里面不能存在两个或多个方法签名一样的方法

## 3、方法重载(overload) 

- java的方法支持重载: **方法名相同, 方法签名不同**

  >  即: 方法名相同, 参数个数不同, 参数类型不同

- 方法重载与返回值类型, 以及方法的参数名无关



## 4 、递归

```
int sum(int n){
	if(n <= 1) return n;
	return n + sum(n - 1);
}
```



# 五、面向对象

## 1、java程序的内存划分

- `堆` 存储GC所管理的各种对象 (就是我们平时new出来的对象)
-  `方法区`  Method Area, 存储每一个类的结构信息(比如字段和方法信息, 构造方法和普通方法) 
- `PC寄存器` Program Counter Register, 存储java虚拟机正在执行的字节码指令地址
- `Java虚拟机栈` Java Virtual Machine Stack, 存储栈帧(java的方法栈) 
- `本地方法栈` Native Method Stack, 用来支持native方法调用(比如C语言编写的方法) 

## 2、构造方法

**构造方法, 也叫构造器, 能够更方便的创建一个对象**

- **方法名必须与类名一样**
- **没有返回值类型**
- **可以重载** 

```
public class Dog{
	public int age;
	public double height;
	
	public Dog(){
	}
	
	public Dog(int age){
		this.age = age;
	}
	
	public Dog(int age, double height){
		this.age = age;
		this.height = height;
	}
}


// 外面使用
Dog d1 = new Dog();
Dog d2 = new Dog(18);
Dog d3 = new Dog(18, 1.88);
```

- **默认构造方法**

  如果一个类没有自定义构造方法, 编译器会自动为他提供无参的默认构造方法

  但是, 如果你自定义了构造方法, 默认的构造方法就不再存在了

## 3、 this

`this` 是一个指向当前对象的引用, 常见用途.

- 访问当前类中定义的成员变量
- 调用当前类中定义的方法**(包括构造方法) ** 

```
public class Dog{
	public int age;
	public double height;
	
	public Dog(int age, double height){
		this.age = age;
		this.height = height;
	}
	
	public Dog(int age){
		//  自己调用自己的构造方法
		this(age, 1.88); // 使用this 调用当前类中的构造方法
	}
}
```

>  this的本质就是一个隐藏的, 位置最靠前的参数



## 4、包 (package)

java中的包就是编程语言中的命名空间, 包的本质是文件夹, 常见的作用是:

- 将不同类进行组织管理, 访问控制
- 解决命名冲突

- 类的第一句代码必须使用`package` 声明自己属于哪个包



java 中, 包名的建议:

- 为了保证报名的唯一性, 一般包名都以公司的域名倒写开头: eg: `com.baidu` 

- 一般包名都是用小写

包名的细节:

- 如果你公司的域名有非法字符(一般是数字, 中划线, 关键字), 建议使用`_` 来使包名合法化

  ```
  520it.com // 域名
  com._520it // 包名
  
  my-name.org // 域名
  org.my_name // 包名
  
  int.com // 域名
  com._int // 包名
  ```

类的第一句代码必须使用`package` 声明自己属于哪个包

```
package com;	// 此处说明当前类 Test 是属于 com 这个包的, 这句不能省

public class Test {

	public static void main(String[] args) {
		System.out.println("======");
	}
}
```



## 5、如何使用一个类

在java中, 要正常的使用一个类, 必须得知道这个类的具体位置(在那个包), 有3种常见的方式来使用一个类:

1. 使用类的全名(包名+类名)
2. 导入包中的具体某个类
3. 导入包中的所有类



- 方式一, 使用类的全名(包名+类名)

  ```
  com.yr.Dog dog = new com.yr.Dog();
  ```

  > 这种使用全名的方式使用类, 肯定是不推荐的, 但是有时也必须要用
  >
  > 当系统内的类(第三方的类)和自己的类名称冲突时, 一般我们会采用这种方式来解决类的冲突
  >
  > 在java开中, 是不存在给类取别名的哈. 

- 方式二, 使用`import` 导入指定的类名

  ```
  import com.yr.Dog; // 导入指定的类名, 后面使用就可以不使用全名了
  
  void test(){
  	Dog dog = new Dog();
  	System.out.println(dog);
  }
  ```

- 使用`import` 导入整个包的所有类

  ```
  import com.yr.Dog;
  import com.yr.Cat;
  // 上面的可以简化为下面的, 直接导入整个包的类, 这样后面包里面的类就不用使用全名了
  import com.yr.*;
  
  void test(){
  	Dog dog = new Dog();
  	Cat cat = new Cat();
  	
  	System.out.println("dog: " + dog + ",cat: " + cat);
  }
  ```

  > 注意:
  >
  > `import com.yr.*;` 只表示导入的com.yr 包中的类, 不包含包中的包, 指的是直接包
  >
  > 即: 
  >
  > import com.yr.*; 仅仅是 import 了直接存放在com.yr 包中的类
  >
  > 并不包含 import com.yr.xx.*; 中的类



## 6、导入的细节

为了方便, java的编译器会为每个源文件,自动导入2个包:

- 第一个, `java.lang.*` 这个包
- 第二个, 当前文件所在的包(即 `文件件所在包.*` 





## 7、继承

### 1、子类 父类同名成员变量

在java中, 子类可以定义跟父类同名的成员变量( 但是, 不推荐这样做) 

```
public class Person{
	public int age = 2;
}

public class Student extends Person{
	public int age = 1;
	public void show(){
		System.out.println(age); 				// 1
		System.out.println(this.age); 	// 1
		System.out.println(super.age);  // 2
		
	}
}
```

> 在其它语言中好像是不允许子类父类有同名的成员变量的



### 2、方法的重写(Override) 

在java中, 子类的方法签名与父类的**方法签名一样** 称为方法重写, 也叫覆盖, 覆写

```
package com;

public class Animal {
	public void speak() {
		System.out.println("Animal speak");
	}
}


package com;
public class Person extends Animal {

	@Override
	public void speak() {
		// TODO Auto-generated method stub
		super.speak(); 
		System.out.println("person speak");
	}
}
```



**java 中方法重写注意点:** 

- 子类`override` 的方法权限, 必须要大于等于`>=` 父类的方法权限

  比如: 父类的方法是`protected`  权限, 子类的就不能比`protected` 小, 只能是`protected或public`

  > public > protected > 无修饰符(package-private) > private

- 子类`override` 的返回值类型必须要小于等于`<=` 父类的方法返回类型

  比如: 父类方法方法是返回`Dog` 子类的就至少是`Dog` 或是`Dog` 的子类



### 3、super

`super` 的常见用途

- 访问父类中定义的成员变量

  ```
  比如: 父类 Animal 和 子类 Person中都有个 `age` 成员变量, 在子类中想要访问父类中的`age` 成员变量就必须使用 super.age 来访问
  this.age; // 访问自己的age
  super.age; // 访问父类的age
  ```

- 访问父类中定义的成员方法

  ```
  public void test(){
  	super.test();
  	System.out.println("child test");
  }
  ```

- 访问父类的构造方法

  > 只能在子类的构造方法中使用super 访问父类的构造方法
  >
  > 且, 使用super调用父类的构造方法时, super只能写在构造方法的第一句

  ```
  Dog(int age, double height){
    super(age);
    this.height = height;
  }
  ```

  

### 4、构造方法的细节

- 子类的构造方法必须先调用父类的构造方法, 再执行后面的代码

- 如果子类的构造方法没有显示调用父类构造方法, 编译器会自动调用父类无参的构造方法

  如果 此时父类没有无参的构造方法编译器将报错.

  > 即, 父类没有无参的构造方法时, 子类的构造方法里面必须显示的调用父类的有参构造方法.



## 8、注解(Annotation)

2个常见的注解:

- `@Override`: 告诉编译器这是一个重写的方法

- `@SuppressWarning("警告类别")` 让编译器不生成警告信息

  ```
  @SuppressWarnings("unused")  // 抑制 未使用警告
  @SuppressWarnings({"unused", "rawtypes})  // 抑制 多个警告
  ```

  > 注意: 
  >
  > 如果你的代码中没有对应的需要压制的警告信息, 但是你使用了对应的抑制 注解, 编译器也会报错

```
// 抑制代码中的单行未使用警告
void test(){
	@SuppressWarnings("unused") 
	int age = 10;
}


// 抑制整个方法中的未使用警告
@SuppressWarnings("unused") 
void test(){
	int age = 10;
	double height = 1.88;
}

// 抑制整个类中的未使用警告
@SuppressWarnings("unused") 
public class Person{
	void test(){ 
    double height = 1.88;
	}
	
	void test2(){
		int age = 10; 
	}
}
```



## 9 、访问控制(Access control)

java中有4个级别的访问控制, 从高到低如下所示:

- `public`: 在任何地方都可见(可访问)
- `protected`: 仅在自己的包中, 自己以及自己的子类中可见(可访问)
- `无修饰符(package-private)` : 仅在自己的包中可见
- `private`: 仅在自己的类中可见

> 在包中可见, 表示的是只要在同一个包里面文件里都是可以访问的, 与子类父类无关
>
> 只要不是被`private` 修饰的, 就是包中可见

![](images/Snip20201010_1.png) 



**使用注意**

- 上述4种访问权限都可以用来修饰类的成员, 比如:

`成员变量` 、`方法` 、`嵌套类` 等

>  所谓的类成员就是写在 java类的 {} 里面的一切

- 只有`public` 、`无修饰符(package-private` 可以修饰顶级类

  > 所谓顶级类, 就是一个源文件中能最外面的类 (因为在 java 中, 可以在类里面定义类)

  ```
  public class Dog{ // 顶级类, 顶级类要么使用public 修饰, 要么不写
  	class Pet{	// 非顶级类
  	}
  }
  ```

- 在java的一个源文件中, 可以写多个顶级类, 但是最多只有一个顶级类可以使用public 修饰,

  且使用 public 修饰的顶级类名必须与源文件名相同

  ```
  // Person.java 源文件
  public class Person{ // 顶级类
  
  }
  
  class Dog{ // 顶级类
  
  }
  
  class Cat{ // 顶级类
  
  }
  
  在java源文件中, 最多只有一个顶级类可以使用 public 修饰
  ```

- 上述4个访问权限不可以修饰 `局部类, 局部变量`



## 10、封装

java中的所谓封装, 一般来说就是将成员变量的访问控制权限全部设置为私有的`private` 然后提供 `get` 和 `set` 方法. 

```
public class Person{
	private int age;
	private double height;
	
	public void setAge:(int age){
		this.age = age;
	}
	public int getAge(){
		return this.age;
	}
	
	public void setHeight(double height){
		this.height = height;
	}
	public double getHeight(){
		return this.height;
	}
}
```

> 顺便说一下,  在java 中尽量为每个类都提供无参的构造方法. 



## 11、toString 方法

- 在java中, 当打印一个对象时, 会自动调用对象的`toString` 方法, 并将返回的字符串打印出来

- `toString` 方法是源于基类`java.lang.Object` , 默认的实现如下所示:

  ```
  // java.lang.Object 类中的toString方法的实现
  
  public String toString() {
  	return getClass().getName() + "@" + Integer.toHexString(hashCode());
  }
  ```

  > 即, 默认情况下我们打印一个对象时,打印结果@的左边表示的是当前对象的类名, @右边表示的是对象的哈希值的十六进制



# 六、static

## 1、static 介绍

- `static` 常用来修饰类的成员: `成员变量`、`成员方法` 、`嵌套类`, 如下: 

  ```
  package com.yr;
  
  public class Person{
  	private static int age;	// static 修饰成员变量
  	
  	public static void run(){	// static 修饰成员方法
  		System.out.println("Person 在 run");
  	}
  	
  	public class Test{	// static 修饰嵌套类
  	
  	}
  }
  ```

  

## 2、static 修饰成员变量、修饰方法

静态变量

- 被`static` 修饰的成员变量, 我们一般称为类变量, 静态变量, 静态字段

  在程序运行的过程中只占用一份固定的内存(存储在方法区)

  - **静态成员变量, 可以通过实例 和 类名 访问** 

- 没有被`static` 修饰的成员变量, 我们称之为实例变量

  在每个实例对象中都有一份实例变量的内存

  - **实例变量, 只能通过实例对象来访问** 



静态方法

- 被`static` 修饰的方法, 称为类方法, 静态方法
  - **静态方法可以通过实例 和 类名访问**
  - **静态方法内部不能使用`this` **
  - **在静态方法里面可以直接访问静态变量 和 静态方法** 
  - **静态方法里面不能直接访问实例变量 和 实例方法** 
- 没有被`static` 修饰的方法, 称为 实例方法
  - **实例方法只能通过实例对象访问** 



不推荐

- 不推荐使用实例方位类变量, 类方法
- 在同一个类中, 不能有同名的实例变量和静态变量
- 在同一个类中, 不能有同名的实例方法和静态方法



## 3、静态导入

### 1、静态导入介绍

使用静态导入后, 就可以省略类名来访问静态成员(静态变量, 静态方法, 嵌套类)

```
// 定义静态 成员的Dog 类
package com.yr;
public class Dog{
	public static int age = 10;
	public static double height = 1.88;
	public static void test(){
		System.out.println("dog static test");
	}
}
```

- 在没有使用静态导入前, 我们是这样用的

  ```
  import com.yr.Dog; // 导入Dog类
  
  public class Person{
  	
  	public static void doTest(){
  		// 访问Dog 中的静态成员我们需要使用实例对象或类名
  		Dog dog = new Dog();
  		System.out.println(dog.age);
  		System.out.println(dog.height);
  		dog.test();
  		
  		// 或者
  		System.out.println(Dog.age);
  		System.out.println(Dog.height);
  		Dog.test();
  	}
  }
  ```

- 使用静态导入后, 我们可以简化静态成员的使用了

  ```
  import com.yr.Dog; // 导入Dog类
  import static com.yr.Dog.age; // 导入Dog类中的age 静态成员
  import static com.yr.Dog.height; // 导入Dog类中的height 静态成员
  import static com.yr.Dog.test; // 导入Dog类中的height 静态成员
  public class Person{
  	
  	public static void doTest(){
  		  
  		System.out.println(age);	// 直接访问静态成员变量
  		System.out.println(height);  
  		test();	// 直接访问静态成员方法
  	}
  }
  ```

  > 其实, 我们也可以使用 `import static com.yr.Dog.*`  静态导入Dog类中的所有静态成员
  >
  > 这样就不用再一个个的导入了



**注意:**

虽然使用静态导入后, 我们在导入类中使用外部的静态成员变得简单了, 但是不要滥用静态导入

引入静态导入使用多了可能也会让我们的代码的可读性降低, 引起不必要的麻烦, 使用时要慎用!!!



### 2、静态导入使用 情景1

没有使用静态导入前

```
package com.yr;
 
class Dog {

	public static int age = 20;
	
	public static void test() {
		System.out.println("dog static test");
	}
	
	
	public static class Leg {
	}
}

// 外部使用
import com.Dog.Leg;

public class Person  {

	public static void main(String[] args) {
		// 需要使用Dog.Leg 来访问
		Dog.Leg leg = new Dog.Leg();
		System.out.println(leg);
	}
}

```

使用静态导入后

```
import com.Dog.Leg;
import static com.Dog.*; // 静态导入


public class Person  {

	public static void main(String[] args) {
		
		Leg leg = new Leg();  // 此处Leg相当于Dog.Leg
		System.out.println(leg);
	}
}
```



### 3、静态导入经典应用场景

```
import static java.lang.Math.PI; // 静态导入 PI

public static void main(String[] args){
	System.out.println(2*PI*3.14);
}
```



## 4、成员变量的初始化

- 编译器会自动为未初始化的成员变量设置初始值

  ```
  public class Person{
  	public static int age;
  	public double height;
  }
  
  // 上面的类中是没有显式的为 age 和 height 成员变量做初始化的
  // 编译器会自动的为我们做初始化
  ```

- 如何手动给实例变量提供初始值?三种方式

  - 在声明的时候就赋初值

  - 在构造方法中

  - 在`初始化块` 中

    编译器会将初始化块复制到每个构造方法的头部`(每创建一个实例对象, 就会执行一次初始化块)`

  ```
  // 声明时候赋初值
  public class Person{ 
  	public double height = 10;
  }
  
  // 构造方法赋初值
  public class Person{ 
  	public double height;
  	public Person(){
  		this.height = 10.0;
  	}
  }
  
  // 初始化块赋初值
  public class Person{ 
  	public double height;
  	
  	// 实例方法, 初始化块
  	{
  		this.height = 10.0;
  	}
  }
  ```

  

- 如何手动给类变量提供初始值? 

  - 在声明中

  - 在 静态初始化代码块 中

    - 当一个类被初始化的时候执行`静态初始化代码块` 

    - 当一个类第一次被主动使用时, JVM 会对类进行初始化

      > 即, 当一个类在第一次被使用的时候就会执行 静态初始化代码块, 也即使静态初始化代码块在程序运行过程中只会执行一次

  ```
  public class Person{
  	public static int age;
  	public Person(){
  	
  	}
  	
  	// 静态初始化代码块
  	static {
  		age = 10;
  	}
  }
  ```



**说明:**

在一个类中, 可以有多个(静态) 初始化代码块, 按照在源码中书写的先后顺序执行





## 5、单例模式

如果一个类设计成单例模式, 那么在程序运行过程中, 这个类只能创建一个实例. 

单例实现的3个 步骤:

1. 构造函数私有化, 禁止外部直接使用构造方法创建实例
2. 提供一个私有的静态的成员变量来保存实例变量
3. 提供一个公共的静态的方法, 供外部来访问单例的实例对象

- 饿汉式单例实现

  ```
  public class Rocket{
  	private static Rocket instance = new Rocket();
  	private Rocket(){}
  	public static Rocket getInstance(){
  		return instance;
  	}
  }
  ```

- 懒汉式单例实现 (有线程安全问题)

  ```
  public class Rocket{
  	private static Rocket instance;
  	private Rocket(){}
  	public static Rocket getInstance(){
  		if(instance == null){
  			instance = new Rocket();
  		}
  		return instance;
  	}
  }
  ```

  



# 七、final



- 被 `final` 修饰的类, 不能被继承

  > 如果你设计出来一个类, 但是不想这个类被别人继承你就可以使用final 修饰这个类

  ```
  public final class Animal { 
  }
  
  // The type Dog cannot subclass the final class Animal
  // 被final 修饰的类不能被继承
  class Dog extends Animal{
  }
  ```

- 被`final` 修饰的方法, 不能被重写

  ```
  public  class Animal {
  	 public final void test() {
  		 System.out.println("animal test");
  	 }
  }
   
  class Dog extends Animal{
  	
  	// 子类不能重写 父类的final 方法
  	@Override
  	public void test() {
  		System.out.println("Dog test");
  	}
  }
  ```

  

- 被`final` 修饰的变量, 只能进行1次赋值操作

  > 其实, java中的fianl 修饰的变量, 和其它语言中`const` 修饰的常量有想同的感觉, 但是又有点不同

  ```
  public void test(){
  	final int age = 10; 
  	age = 20; // 错误, final 修饰的变量只能赋值一次
  }
  
  public void test(){
  	final int age ; 
  	age = 10; // final 修饰的变量只能赋值一次, 可以先定义在赋值, 反正只能赋值一次
  }
  ```

  - 如果`final` 修饰的是类的成员变量时, 除了 这个成员变量只能赋值一次外, 还要求对象创建出来后final修饰的成员变量就要有值

    ```
    // 错误写法
    public class Dog{
    	private final int age;
    }
    
    // 正确写法1
    public class Dog{
    	private final int age = 10;
    }
    
    // 正确写法2
    public class Dog{
    	private final int age;
    	
    	{
    		age = 10;
    	}
    }
    
    // 正确写法3
    public class Dog{
    	private final int age;
    	
    	public Dog(){
    		age = 10;
    	}
    }
    
    即, final修饰成员变量时, 在实例对象创建出来时必须有值
    要么定义成员变量是赋值, 要么在构造方法里赋值, 要么在初始化代码块中赋值
    ```

    > 当然, final修饰的成员变量, 也可以是静态成员变量(静态方法), 用法类似



**补充**:

想java中这种final 修饰的变量, 一旦赋值了就不能再赋值了, 在其它语言中称为**常量** , 但是在java开发中我们一般所说的常量不是这个final 修饰的变量,如: `final int age = 10;` 

在java中我们所说的常量一般更多指的是下面这种, 这种我们一般才称为常量:

```
// 下面这种才是我们一般称为的java常量
public static final double PI = 3.141592653589;

// 即在java中我们所说的常量一般指的是被 static final 修饰的 静态成员变量
// 且, java中的常量一般全部使用 大写命名, 多个单词使用 _ 分隔
```



**java 常量常识:**

- 如果将基本数据类型或者字符串定义为常量( static final) , 并且在编译时就能确定值

  编译器会使用常量值替代各处的常量名(类似于C语言中的宏替换)

  ```
  public  class Animal {
  	
  	private  final static int AGE = 10; // 这种一般我们成为编译时常量 
  	 
  	 public static void test() {
  		 System.out.println(AGE); // 编译器会自动替换为   System.out.println(10);
  	 }
  }
  
  // 但是想下面这种是不会替换的
  
  public  class Animal {
  	
  	private  final static int AGE = getAge();
  	static int getAge(){
  		// 计算操作 ...
  		reture 10;
  	}
  	 
  	 public static void test() {
  		 System.out.println(AGE); // 此处编译器不会自动替换为   System.out.println(10);
  	 }
  }
  ```



# 八、嵌套类(Nested Class)



## 1、嵌套类介绍

- 嵌套类: 定义在另一个类中的类

  ```
  public class OuterClass{
  	// 静态嵌套类
  	static class StaticNestedClass{
  	
  	}
  	
  	// 非静态嵌套类(内部类)
  	class InnerClass{
  	
  	}
  }
  ```

  > 只要是定义在一个类内部的类, 不论有没有被static修饰, 我们都称为嵌套类
  >
  > 使用 static 修饰的嵌套类, 称为静态嵌套类
  >
  > 没有被static修饰的嵌套类, 称为非静态嵌套类(或者 内部类)

- 定义在嵌套类外面的类 , 我们称为: 外部类(outer class) , 像上面的 `OuterClass` 就是外部类

- 最外层的外部类, 称为: 顶级类(top-level class)

  ```
  public class Person{	// 顶级类
  	class A{	// 外部类
  		class B{	// 外部类
  			class C{
  			}
  		}
  	}
  }
  ```

  



## 2、内部类(inner class)

- 内部类, 没有被`static` 修饰的嵌套类(非 静态嵌套类)

- **跟 实例变量, 实例方法一样, 内部类与外部类的实例对象相关联** 

  > 说白了, 内部类(非 静态嵌套类) 和实例变量, 实例方法一样, 只能通过实例对象的方式访问, 如果没有创建外部内的实例变量是不能访问内部类
  >
  > 注意: 我们此处说的内部类, 都是指的 非静态嵌套类, 静态嵌套类后面再说.

  ```
  package com.yr;
  
  public class Person{
  	private int age;
  	public int getAge(){
  	
  	}
  	class InnerClass{
  	
  	}
  }
  
  说白了, 要访问 `age`, `getAge()`, `InnerClass`  这三个成员都必须先创建 Person 类的实例对象, 这也就是我们说的与实例对象挂钩
  其实很好理解, Person类的实例不存在时, `age` 不存在, 没有人调用`getAge()` 方法, `InnerClass` 没有意义
  ```

- ​	**必须先创建外部类实例, 然后再用外部类实例创建内部类实例** 

  ```
  package com.yr;
  
  public class Person{
  	private int age;
  	public int getAge(){
  		return age;
  	}
  	
  	public class Hand{
  		public void test(){
  			System.out.println("person innerclass hand");
  		}
  	}
  }
  
  Public class Test{
  	public static void main(String[] args){
  		// 1. 创建Person实例对象
  		Person person = new Person();
  		
  		// 2. 通过Person 的实例对象创建内部类 Hand 的实例对象
  		Hand hand = person.new hand();	// 注意, 只能通过这种方式创建Hand 的实例
  		hand.test(); // 通过Hand 的实例访问里面的实例方法
  	}
  }
  ```

  > 其实, 在内部类里面是有一个指向外部类的引用的(相当于你可以理解为在内部类里面有个外部类的成员变量), 上面示例的内部类的内存布局如下: 

  ![](images/Snip20201013_4.png) 

  从上面内部类的内存结构, 我们也可以理解为什么, 必须要先创建外部类对象后才能创建内部类对象. 

  

- 内部类不能定义 除 **编译时常量** 以外的任何 **static 成员** 

  ```
  public class Person{
  	public class Hand{
  		private static  final int weight = 188; // 编译时常量  
  		// 错误写法, 在内部类中 定义的静态变量 必须是final 修饰的常量
  		// private static int count = 10;
  	}
  }
  ```

  

- 内部类可以直接访问外部类中的所有成员(即使被声明为 private)

  ```
  public class Person  {
  	private int age = 18;
  
  	class Hand{
  		 void test() {
  		 // 内部类, 访问外部类 的私有成员变量也是可以的
  			System.out.println(age); // 此处相当于是 访问 person.age
  			
  		}
  	}
  	
  	public static void main(String[] args) {
  		Person person = new Person();
  		Hand hand = person.new Hand();
  		hand.test();	
  	}
  }
  ```

  

- 外部类可以直接访问内部类实例的成员变量, 方法(即使声明为 private)

  ```
  public class Company{
  	private String name;
  	public Company(String name){
  		this.name = name;
  	}
  	
  	public void fire(Employee e){
  		// 外部类访问内部类的私有成员
  		System.out.println(name + "fire " + e.no );
  	}
  	
  	public class Employee{
  		private int no;
  		public Employee(int no){
  			this.no = no;
  		}
  	}
  	
  	public void show(){
  		// 内部类访问外部类的私有成员变量
  		System.out.println(name + ": " +no);
  	}
  }
  ```

  > 即内部类和外部类可以相互访问对方的成员.

## 3、内部类细节

当外部类与内部类有相同的成员变量时, 需要按照下面的方式访问

```
public class OuterClass{
	private int x = 1;
	
	public class InnerClass{
		private int x = 2;
		public void show(){
			System.out.println(x); // 2
			System.out.println(this.x); // 2
			System.out.println(OuterClass.this.x); // 1
			
		}
	}
}
```



## 4、静态嵌套类 (static Nested Class)

- 静态嵌套类: `被 static 修饰的嵌套类`

- 静态嵌套类在行为上就是一个顶级类, 只是定义静态嵌套类的代码写在了另一个类中了而已.

  ```
  public class Person{
  	private int age = 10; 
  	// 在Person这个类中定义了一个 static的静态嵌套类
  	public static class Car{
  	}
  }
  
  // 外部使用静态嵌套类
  public static void main(String[] args){
  
  	Person tom = new Person();
  
  	// 静态嵌套类需要这样使用, 直接使用类名 . 即可, 不用向内部类一样需要创建外部类的实例
  	Person.Car myCar = new Person.Car();
  	// 可以从上面的代码看出, 静态嵌套类的行为就是一个顶级类. 
    // Car 对象和 Person 对象没有任何联系
  }
  ```

- 对比一般的顶级类, 静态嵌套类多了一些特殊权限

  **可以直接访问外部类中的成员(即使被声明为 private) **

  ```
  public class Person{
  	private static int age = 10;
  	private int count = 2;
  	private static void run(){
  		System.out.println("person run");
  	}
  	public static class Car{
  		public void test(){
  			Person person = new Person();
  			System.out.println(person.count);	// 访问person实例的私有成员
  			System.out.println(Person.age); 	// 可以直接访问外部类的静态成员变量, 即使是私有的
  			Person.run(); 	// 可以访问外部类的静态方法, 即使是私有的
  		}
  	}
  }
  
  // 外部使用静态嵌套类
  public static void main(String[] args){
   
  	Person.Car myCar = new Person.Car();
  	myCar.test();
  }
  ```

  

## 5、什么情况下使用嵌套类呢? 

首先要回答这个问题, 我们必须先搞懂下面的问题: 

1. 嵌套类分为静态嵌套类和非 静态嵌套类(内部类)

2. 静态嵌套类相当于普通的顶级了, 可以独立于外部类, 单独创建自己的实例对象, 只是静态嵌套类相比普通的定义类多了一些方位外部类成员的权限

3. 非 静态嵌套类, 我们也称为内部类, 在内部类的内部其实是有一个隐藏的指向外部类的引用, 因此必须要先创建外部类的实例, 再通过外部类的实例才能创建内部类的对象

   



**使用嵌套类的经验总结:**

- 如果 `类A` 只用在 `类C` 的内部, 可以考虑将 `类A` 嵌套在 `类C` 中

  - 封装性更好, 对于类A外部是永远不可见的
  - 程序的包更加的简化(程序对外看起来类更少, 更简单) 
  - 这样处理, 有时增强可读性和可维护性

- 如果 `类A` 需要经常访问 `类C` 的非公共成员, 可以考虑将 `类A` 嵌套到 `类C` 中. 

  > 因为调用方法会经常的分配栈帧, 回收栈帧, 频繁的调用方法也会消耗性能, 如果直接访问成员的话性能会更好 

- 另外, 如果是想将`类A` 隐藏起来, 也是可以考虑将 `类A` 作为 `类C` 的嵌套类, 不对外暴露

- 如果需要经常访问非公共的实例成员,  设计成内部类(非静态嵌套类), 否则设计成静态嵌套类. 

  > 即, 我们在设计静态嵌套类时, 尽量设计成 静态嵌套类
  >
  > 即, 能静态就静态 



# 九、局部类(local Class)

- 局部类: 定义在代码块中的类(可定义在`方法中`、`for循环中` 、`if语句中等`) 

  ```
  public class Person{
  	public void test(){
  		class A{
  		
  		}
  	
  		if(ture){
  			class B{
  			
  			}
  		}
  		
  		for(int i=0; i<10; i++){
  			class C {
  			
  			}
  		}
  	}
  }
  ```

- 局部类的特点:

  - 局部类的作用域, 只在当前定义局部类的代码块中有效

    ```
    if(true){ // class A 只能在这个{} 内可以使用
    	class A{
    	
    	}
    }
    ```

  - 局部类不能定义除编译时常量以外的任何 static 成员

    ```
    void test() {
    		class A{
    			static final int Type = 1;
    			int aa = 10; 
    			// static int a = 10; 错误, 只能定义编译时常量, 即 static final 修饰的成员
    		}
    	}
    ```

  - 局部类只能访问 `final` 或者 有效 `final` 的局部变量

    ```
    void test() {
    
    		int aa = 10; // 此处的 aa 相是 有效 final 的局部变量
    		// 在java8以前, 这里是必须写成 final int aa = 10; 的, 否则报错
    
    		// 编译器, 判断局部变量只赋值过一次时, 就认为局部变量是 有效final局部变量
    		// 即, 此处 int aa = 10; 相当于 final int aa = 10;
    		class Test{
    			 void testA() {
    				 System.out.println(aa);
    			 }
    		} 
    		
    		Test t = new Test();
    		t.testA(); // 此处调用testA时, 可能外部的局部变量 aa 已经回收了, 所以 testA 内部的aa 需要是有效final的类型 加持
	}
    ```
    
    > 其实, 你可以将局部类内部访问的有效 final局部变量理解为在局部类里面有对外面的有效final
    >
    > 有值捕获的意思, 防止外部修改
    >
    > 因为他要考虑到函数调用时堆栈内存回收的问题等等, 所以从这样来理解的话是合理的
    
  - 局部类可以访问外部类里面的成员, 即使被定义为私有
  
    - 局部类只有定义在实例相关的代码块中, 才能直接访问外部类中的实例成员(实例变量, 实例方法)
  
    ```
    package com;
    public class Person{
    	private int age = 10;
    	public static void main(String[] args) {}
    	
    	void test() {
    		if (true) {
    			// 局部类
    			class Test{
    				void test() {
    					// 局部类方位外部类的 私有成员呢
    					System.out.println(age);
    				}
    			}
    		}
    	}
    ```
  
    - 注意: 
  
      ```
      public class Person{
      	private int age;
      	
      	// 实例代码块, 这样是可以的
      	{
      		class Dog {
      			void speak(){
      				System.out.println(age);
      			}
      		}
      	}
      	
      	// 静态代码块, 这样是不可以, 不和示例挂钩
      	{
      		class Dog {
      			void speak(){
      				System.out.println(age);  // 报错, 静态代码块不与实例挂钩
      			}
      		}
      	}
      }
      ```
  
- 局部类举例

  ```
  public class TestLocalClass{
  	private int a = 1;
  	private static int b = 2;
  	private static void test1(){}
  	private void test2(){}
  	
  	// 局部类
  	public void test3(){
  		int c = 3;
  		class LocalClass{
  			static final int d = 4;
  			void test4(){
  			 System.out.println(a+b+c+d);
  			 test1();
  			 test2();
  			}
  		}
  		
  		new LocalClass().test4();
  	}
  	
  }
  ```

  



# 十、抽象类 & 接口



## 1、抽象方法 (Abstract Method)

在学习抽象类之前, 我们先来看一下抽象方法

- 被 `Abstract` 修饰的方法, 称为抽象方法

  - 且, 抽象方法只有方法声明, 没有方法实现(即, 参数列表后面没有 `{}` , 只有分号)
  - 且, 抽象方法不能是 `private` 权限, 因为定义抽象方法的目的就是让子类去实现的, 如果使用`private` 修饰的话, 那么子类是不能访问的, 这样就矛盾了
  - 且, 抽象方法, 只能是实例方法, 不能是静态方法(类方法)
  - 且, 抽象方法只能定义在抽象类, 或者是接口中(因为抽象类是提供给子类继承实现, 接口时用给其它类实现的, 实现时重写对应 抽象方法) 

  ```
  package com;
  // 抽象类
  public abstract class Animal {
  	// 抽象方法
  	public abstract void run();
  }
  ```



## 2、抽象类

- 抽象类: 被`abstract` 修饰的类, 称为抽象类

  - 抽象类不被 被 `final` 修饰( 因为定义抽象类的目的就是给子类继承的, 而被`final` 修饰的类是不能被继承的, 因此抽象类不能`final` 修饰)
  - 抽象类中, 可以定义抽象方法 (被 `abstract` 修饰的方法)
  - 抽象类不能实例化, **但是抽象类可以自定义构造方法** 
    - 抽象类定义构造方法的意义, 就是让子类调用父类的构造方法的意义
  - 子类必须实现抽象类中的抽象方法(即, 子类必须重写抽象类中的抽象方法), 除非子类也是抽象类
  - 可以像非抽象类一样定义成员变量、常量、嵌套类型、初始化块, 非抽象方法等
    - 也就是说, 抽象类完全可以不定义抽象方法

  >  简单的记, 抽象类就是在普通的类的基础上增加了可以定义抽象方法的功能
  >
  > 也减少了一个功能, 就是实例化的功能

  ```
  package com;
  
  public abstract class Animal {
  	
  	public abstract void run();
  }
  
  // 抽象子类可以不实现父类的抽象方法
  abstract class Bird extends Animal{
  	public abstract void fly();
  }
  
  // 普通子类必须实现父类的抽象方法
  class Dog extends Animal{
  	@Override
  	public void run() {
  		// TODO Auto-generated method stub	
  	}
  }
  ```



## 3、接口 (interface)

### 1、接口的介绍

- java 中的接口: 

  一系列方法声明的集合, 是用来定义规范和标准的

  ```
  package com;
  public interface TestInterface {
  	public abstract void test();
  }
  ```

  > 一句话, java中的接口就是用来定义方法声明的
  >
  > 如果, 按照这么说的话,那么java中的接口和抽象类是很像的, 但是java中的接口和抽象类还是有区别的, 具体区别我们后面说

- java 接口可以定义的内容

  - 可以定义`抽象方法`、`常量`、 `嵌套类`, 从java8开始可以定义`默认方法`、`静态方法(类方法)`

    > **注意**: 
    >
    > 1. 在接口中定义的 `抽象方法`、`常量`、`嵌套类` 都是隐士的 **public** 的, 因此在接口内定义`抽象方法, 常量, 嵌套类` 是都时可以省略 **public** 关键字
    >
    > 2. 但是, 从java9开始, 接口中可以定义 `private` 的方法, 因为现在很多人都是使用的java8. 所以在接口中定义`private` 方法这种是不太常见的做法, 且容易出现兼容性问题
    >
    > 3. 在接口中定义的常量可以省略 `static final` , 换句话说, 在接口中定义常量可以写成`static final int AGE = 10, 与 int AGE = 10` 等价
    >
    >    *因为在接口中定义的常量是可以省略 `static final` 的, 换句话说在接口中只能定义常量, 不能定义变量*
    >
    > 4. 接口中定义的抽象方法也可以省略`abstract` 关键字, 换句话说在接口中定义的方法默认就被加上你了 `public abstract` 修饰符
    >
    >    *换句话说, 在抽象类中定义的抽象方法必须写`abstract` 关键字, 在接口中定义的抽象方法可以省略 `public` 和 `abstract` 关键字
    >
    > 5. 接口中是不能定义构造方法, 不能定义(静态) 初始化块, 不能实例化

    

  ```
  public interface JiaJiaoable{
  	// 1. 接口中定义常量
  	static final int AGE = 10; // 相当于是 public final int AGE = 10;
  	// 2. 定义抽象方法
  	abstract void jiaoBianChenng(Kid kid);	
  	// 相当于是 public abstract void jiaoBianChenng(Kid kid);
  	// 3. 定义嵌套类
  	class A{}  // 相当于是 public class A{}
  	
  }
  ```

- 示例代码

  - 接口代码

    ```
    package com;
    
    public interface JiaJiaoable {
    	// 在接口中可以定义 常量 (static final)
    	static final int AGE = 10;
    	// 因为在接口中定义常量可以省略 static final, 因此上面这句可以简写为 int AGE = 10;
    
    	public abstract void jiaoBianCheng(Child child);
    	// 因为在接口中定义的方法默认就是 public abstract 的, 因此上面方法的定义可以简写为
      // void jiaoBianCheng(Child child);
    }
    ```

  - 实现接口的类

    ```
    package com;
    
    public class Student implements JiaJiaoable {
    
    	@Override
    	public void jiaoBianCheng(Child child) {
    		
    		System.out.println("Student jiao " + child.getName() + "biancheng");
    	}
    }
    ```

  - 外部代码

    ```
    package com;
    
    public class Child {
    	private String name;
    	private JiaJiaoable jiaJiao;
    	public Child(String name) {
    		this.name = name;
    	}
    	
    	public String getName() {
    		return name;
    	}
    	
    	public void setJiaJiao(JiaJiaoable jiaJiao) {
    		this.jiaJiao = jiaJiao;
    	}
    	
    	
    	public void study() {
    		// 通过 接口的实例对象, 访问接口内定义的常量
    		System.out.println(jiaJiao.AGE);
    		// 通过接口名访问, 接口中的常量
    		System.out.println(JiaJiaoable.AGE);
    		this.jiaJiao.jiaoBianCheng(this);
    	}
    	
    	
    	 public static void main(String[] args) {
    		 Child child = new Child("zhangsan");
    		 child.setJiaJiao(new Student());
    		 child.study();
    		 
    	 }
    }
    ```



**接口总结:**

```
public interface JiaJiaoable{
	public static finale int AGE = 10;
	public abstract void jiaoBianCheng();
	public class A{}
}

// 与下面的代码完全等价
public interface JiaJiaoable{
	int AGE = 10;
	void jiaoBianCheng();
	class A{}
}
```



### 2、接口的细节

- 接口的名称可以在任何使用类型的地方使用 (表示具备某种能力的对象)

- 一个类可以通过`implements` 关键字实现一个或者多个接口(多个接口之间使用`,` 分隔)

  - 实现接口的类必须实现接口中所有的抽象方法, 除非这个类是抽象类
  - 如果一个类实现的多个接口中有相同的抽象方法, 只需要实现一次

- `extends` 和 `implements`  可以一起使用, 且`implements` 关键字必须写在 `extends` 的后面

  - 当父类, 接口中的方法签名一样时, 那么返回值类型也必须一样

- 一个接口可以通过`extends` 关键字继承一个或多个接口

  - 当多个父接口中的方法签名一样时, 那么返回值类型也必须一样

  ```
  // 在java中接口也是可以继承的
  public interface Happiable extends Eatable, Runnable{
  	
  }
  ```



### 3、抽象类和接口的对比

- 首先抽象类很容易理解, 抽象类就是在普通的类的基础上增加了定义抽象方法的能力
- 抽象类是对一类事物的概括描述, 继承自抽象类的子类都有一些共性
- 接口是对某些事物具备某种能力的描述, 实现抽象类的类都具备某种能力

- 抽象类是用来继承的 (extends)
- 接口是用来实现的(implements)

**何时选择抽象类呢?**

1. 在紧密相关的类之间共享代码时, 选择抽象类
2. 需要使用除`public` 之外的权限时使用抽象类. (因为接口中的都是public)
3. 如果需要定义实例变量, 非final的静态变量使用抽象类 (因为接口中定以的成员变量默认就是常量 static final)

**何时选择接口**?

1. 不相关的类实现相同的方法, 选择接口
2. 只定义行为, 不关心具体谁实现, 选择接口
3. 如果要实现类型的多继承(能力的多继承), 选择接口 (类只能是单继承) 



### 4、接口的升级问题

前面, 我们已经介绍过了, 接口表示的是能力清单, 功能清单, 一个类实现了某个接口就代表具备了某类能力. 接口是用来给外部的类实现的, 如果我们在项目的开发后期想要为某一个接口增加抽象方法怎么办呢? 这时其实挺麻烦的, 因为我们可能并不知道那些类实现了对应的接口, 我们不可能将项目中所有的类挨个找一遍吧, 这个似乎不太现实, 而且也容易出错.  这就是我们要解决的一个接口升级问题.

如果我们想要在不改动以前的实现类的前提下进行接口的升级, 从java8开始, 有2种方案:

- 方案一: 为接口新增 **默认方法 default method**
- 方案二: 为接口新增 **静态方法 static method** 



#### 1、接口默认方法( default method)

- 用`default` 修饰的方法是 `默认方法`

  - 默认方法只能是 `实例方法`

    ```
    public interface Eatable{
    	// 为接口增加默认方法
    	default void eat(String name){
    		System.out.println("Eatable 吃 " + name);
    	}
    }
    
    // 子类实现接口并重写接口的默认方法
    public class Person implements Eatable{
    	@Override
    	default void eat(String name){
    		// 实现类通过 接口名.super调用接口的默认实现
    		Eatable.super.eat(name);
    		System.out.println("Person 吃 " + name);
    		
    	}
    }
    ```

- 当一个类实现了的接口中有默认的方法实现时

  - 这个类可以啥也不干, 沿用接口的默认实现 (这也是我们使用默认方法升级接口的原理)
  - 当然, 实现类也可以重写接口中的默认实现方法
  - **当然, 子类也可以将接口中的默认方法声明为抽象方法(此类必须是抽象类)**

- 当一个接口继承自另外一个接口时

  - 子接口可以将父接口中的抽象方法, 重新定义实现为默认方法
  - 子接口也可以将父接口中的抽象方法, 重新定义为默认方法



#### 2、接口默认方法的细节

- 如果父类定义的非抽象方法 与 接口的默认方法相同时, 最终调用父类的方法

  > 及优先调用类中的方法, 在查找接口中的默认方法
  >
  > 即, 如果一个类实现了一个接口的话, 如果实例对象 调用接口中声明的方法时, java 会优先查找类中的实现会调用类中实现的方法(从子类往父类查找), 如果类中没有实现才查找接口中有无默认实现并调用, 否则报错

  ```
  // 接口中定义了一个 默认方法 run
  package com;
  public interface Runable {
  	default void run() {
  		System.out.println("runable interface default run");
  	}
  }
  
  // 父类中定义了一个 run 方法
  public class Animal {
  	public void run() {
  		System.out.println("Animal run");
  	}
  }
  
  // 子类继承父类, 并实现了接口
  public class Person extends Animal implements Runable {}
  
  // 执行代码
  public class Child {
  	
  	 public static void main(String[] args) {
  		 Person person = new  Person();
  		 person.run(); // 最终执行的是 父类中的 非抽象方法 "Animal run"
  	 }
  }
  ```

- 如果父类中定义的抽象方法与接口中定义的默认方法相同, 要求子类必须实现此抽象方法

  > 子类在实现父类的抽象方法时可以使用 接口名.super 关键字, 调用接口中的默认方法

  ```
  // 接口定义默认方法
  public interface Runable {
  	default void run() {
  		System.out.println("runable interface default run");
  	}
  }
  
  // 父类定义 抽象方法与 接口中定义的默认方法相同
  public abstract class Animal {
  	public abstract void run() ;
  }
  
  // 子类必须实现父类的抽象方法, 即便实现的接口中有定义相同的默认方法
  // 当然, 子类在实现父类的抽象方法时, 如果不想自己实现, 可以使用 接口名.super 调用接口中的默认实现
  public class Person extends Animal implements Runable {
  	public void run() {
  		Runable.super.run();
  	}
  }
  
  // 应用
  public static void main(String[] args) {
  		 Person person = new  Person();
  		 person.run(); // 此处最终调用的是接口中的默认实现
  	 }
  ```

- 如果一个子接口继承自多个父接口, 且多个父接口都有共同的默认方法, 那么要求子接口必须对同名的默认接口进行重写(重新实现一个同名的默认方法, 或是将同名的默认方法重写为一个抽象方法)

  > 其实很好理解, 因为多个父接口中都有一个相同的默认实现, 子接口在调用这个名字的方法时根本不知道该调用哪一个, 在子接口层级处理好这个分歧即可

  ```
  // 1. Runnable 接口定义了一个默认方法 run
  public interface Runnable{
  	default void run(){
  		System.out.println("Runnable run");
  	}	
  }
  
  // 2. Walkable 接口中也定义了一个默认方法 run
  public interface Walkable{
  	default void run(){
  		System.out.println("Walkable run");
  	}	
  }
  
  // 3. Testable 继承自 Runnable 和 Walkable
  // 那么子接口必须重写 父接口的 默认方法
  public interface Testable extends Runnable, Walkable {
  	@Override
  	default void run() { 
  		Runnable.super.run();
  		Walkable.super.run();
  	}
  }
  ```

- 同理, 如果是一个类实现多个接口时, 如果多个接口都有同名的默认实现也是要求类重写这个默认的方法

  > 同理, 因为多个接口都有同名的默认实现, 实例在调用时有歧义, 不知道调用哪个, 子类实现即可

  ```
  // 1. Runnable 接口定义了一个默认方法 run
  public interface Runnable{
  	default void run(){
  		System.out.println("Runnable run");
  	}	
  }
  
  // 2. Walkable 接口中也定义了一个默认方法 run
  public interface Walkable{
  	default void run(){
  		System.out.println("Walkable run");
  	}	
  }
  
  // 3. Testable 继承自 Runnable 和 Walkable
  // 那么子接口必须重写 父接口的 默认方法
  public class Test implements Runnable, Walkable {
  	@Override
  	public void run() { 
  		Runnable.super.run();
  		Walkable.super.run();
  	}
  }
  ```

- 像下面这种接口继承方式, 又都有默认方法时, 是不要求重写的

  ```
  // 1. Animal 接口中定义了默认方法
  public interface Animal{
  	default String mySelf(){
  		return "animal mySelf";
  	}
  }
  
  // 2. Fire继承自Animal 但是 自己里面未设置 默认方法
  public interface Fire extends Animal{
  }
  
  // 3. Fly 继承自Animal, 并且有自己的默认方法
  public interface Fly extends Animal{
  	default String mySelf(){
  		return "Fly mySelf";
  	}
  }
  
  // 这种, Fly 和 Fire 中没有直接的默认方法, 实现类就可以不用再重写了
  public class Dragon implements Fly, Fire{
  	
  }
  Dragon dragon = new Dragon();
  System.out.println(dragon.mySelf());  // 打印的是 "Fly mySelf"
  
  ```

- 在接口中定义的抽象方法, 类是必须要全部实现的, 没有像Objective-c中的协议中有可选的这种语法

  除非是接口中定义的默认方法类可以不实现

#### 3、静态方法 (static method)

前面说过了, 我们为已有的接口实现升级操作主要有两种方式: `增加默认方法 和静态方法` , 下面我们就来看一下如何通过给接口添加静态方法来升级接口



- **接口中定义的静态方法与类中定义的静态方法有点不同, 在接口中定义的静态方法只能通过接口名字调用, 且接口中定义的 静态方法不能被继承**

  在类中定义的静态方法, 既可以通过类名调用, 也可以通过实例调用(不推荐)

- 类中定义的静态方法是可以被继承的, 但是接口中定义的静态方法是不能被继承的

  > 换句话说, 静态方法定义在那个接口中就只能通过那个接口名来调用, 不能使用子接口名或对应的实例来调用

  ```
  public class Person {
  	public static void run() {
  		System.out.println("Person static run");
  	}
  }
  
  public class Student extends Person {}
  
  public class Child {
  	 public static void main(String[] args) {
  		 Student.run(); // 结果是 "Person static run"
  	 }
  }
  
  ```

  > 我们来探讨一个问题? 为什么类中定义的静态方法可以使用`类名` 、`子类名` 、`类的实例对象`、`子类的实例对象`来调用,  而接口中定义的静态方法只能使用定义静态方法的接口名来调用呢? 
  >
  > 其实, 这个问题也很好回答.
  >
  > 1. 因为接口是可以多继承的, 如果子接口继承的多个父接口中都定义了相同名字的静态方法, 那么通过子接口名调用静态方法时, 编译器是有歧义的, 这是原因之一
  > 2. 因为类在实现接口时, 也是可以同时实现多个接口的, 如果类实现的多个接口有相同的静态方法时, 实例对象在调用时, 编译器也是有歧义的, 这是原因之二
  > 3. 因为类是单继承的, 通过类名或者类的实例时, 从子类向父类沿着一直找, 是没有歧义的.



# 十一、多态 ( polymorphism)

## 1、多态介绍

其实在很多编程语言里面, 都是有多态的. 

- 什么是多态?
  - 具有多种形态
  - 同一操作用于不同的对象, 产生不同的执行效果
- 多态的体现
  - 父类(接口) 类型指向子类实例对象
  - 调用子类重写的方法
- JVM会根据引用变量指向的具体对象来调用对应的方法
  - 这个行为叫做: `虚方法调用(virtual method invocation)`
  - 类似C++中的虚函数调用



## 2、继承时多态应用

- 我们首先来看一个类继承时, 多态的体现

  ```
  package com;
  
  public class Animal {
  
  	public void speak() {
  		System.out.println("animal speak");
  	}
  	
  	public static void main(String[] args) {
  		Animal catAnimal = new Cat();
  		catAnimal.speak(); // 真正调用时会调用 Cat 的speak, 这就是多态的体现
  	}
  }
  
  class Dog extends Animal{
  	@Override
  	public void speak() {
  		super.speak();
  		System.out.println("Dog speak");
  	}
  }
  
  class Cat extends Animal{
  	@Override
  	public void speak() { 
  		super.speak();
  		System.out.println("Cat speak");
  		
  	}
  }
  ```



## 3、接口多态应用

- 我们再来看一个类实现接口时, 多态的体现

  ```
  package com;
  public interface Runnable {
  	void run();
  }
  
  public class Person implements Runnable {
   
  	public void run() {
  		System.out.println("person run");
  	}
  }
  
  class Student implements Runnable{
  	public void run() {
  		System.out.println("student run");
  	}
  }
  
  public static void main(String[] args) {
    Runnable run1 = new Person();
    run1.run();	// "person run"
  
    Runnable run2 = new Student();
    run2.run(); // "student run"
  }
  ```

## 4、静态方法, 多态应用






























