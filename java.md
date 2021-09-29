# 诞生

​	1995	Java的第一个版本

​	Gosling

# Java语言是解释性语言

​	解释性语言：编译后的代码不能直接被机器执行，需要解释器来执行

​	编译性语言：编译后的代码可以直接被机器执行



# 转义字符

​	\r	回车	光标回到本行行首，如果\r后面还有输出内容，将会从行首开始替换



# 注释

​	多行注释不能嵌套

## 	javadoc注释

​		注释内容可以被JDK提供的工具javadoc所解析，生成一套以网页文件形式体现的该程序的说明文档

​		形式

```java
/**
*
*
*/
```

​		javadoc -d 文件夹名 -xx -yy Demo3.java

​		javadoc -d 文件夹名 -author -version Demo3.java



# Java代码规范

​	类，方法的注释，使用javadoc的方式，即文档注释

​	非javadoc注释，往往是对代码的说明（给程序的维护者），说明如何修改，注意事项

​	行尾风格

```java
		左大括号在代码下一行行首{

		}
```

​	次行风格

```java
		左大括号在代码行尾

		{

		}
```



# DOS命令

​	md d:\\\temp	在D盘下创建temp文件夹

​	rd d:\\\temp	在D盘下删除temp文件夹

​	echo ok > pic.txt	将ok输入到pic.txt文件中，如果pic.txt文件不存在则创建一个名为pic的txt文件

​	echo nul > pic.txt	创建一个名为pic的txt空文件

​	copy ok.txt e:\ok.txt	拷贝ok.txt到e盘（拷贝后的文件名可以更改）

​	move ok.txt e:\ok.txt	将ok.txt文件移动到e盘

​	del pic.txt	删除pic.txt文件

​	dir	查看当前目录下有什么内容

​	C:	or	cd /D c:	切换到C盘

​	cd ..	切换到上一级目录

​	cd \	切换到根目录

​	tree	d:	查看D盘下面的所有内容

​	cls	清屏

​	exit	退出



# sublime编写Java源程序

​	由于DOS窗口采用的是GBK的编码格式，所以如果想要在DOS窗口中运行sublime编写的Java源程序，需要在源程序编写完成之后使用GBK的编码格式进行保存



# JDK、JRE、JVM三者之间的关系

​	JDK = JRE + java开发工具

​	JRE = JVM + 核心类库



# 用户变量与系统变量之间的区别

​	用户变量只针对当前用户有效，系统变量针对所有用户都有效



# 变量

​	三要素

​		变量 = 变量名 + 值 + 数据类型



# +的使用

​	当左右两边是数值类型时，做加法运算

​	当左右两边有一边是字符串时，做字符串拼接运算

​		注：运算顺序从左到右



# 数据类型

## 基本数据类型

### 数值型

#### 整数类型：存放整数

​	字节	byte[1]	-128 ~ 127

​	短整型	short[2]	-2^15 ~ 2^15-1	-32768 ~ 32767

​	整型	int[4]	-2^31 ~ 2^31-1	-2147483648 ~ 2147483647

​	长整型	long[8]	-2^63 ~ 2^63-1

​	注：	

​		Java的整形常量（具体值）默认为int型，声明long型常量后须加‘l’或者‘L’

​		bit：计算机中最小的存储单位

​		byte：计算机中基本存储单元	1byte = 8bit

#### 浮点（小数）类型

​	单精度	float[4]	-3.403E38 ~ 3.403E38

​	双精度	double[8]	-1.798E308 ~ 1.798E308

​	注：

​		浮点数在机器中存放形式的简单说明：浮点数 = 符号位 + 指数位 + 尾数位

​		尾数部分可能丢失，造成精度损失（小数都是近似值）

​		Java的浮点型常量默认为double型

​		声明float型常量，须后加‘f’或者‘F’

​		浮点型常量的两种表现形式

​			十进制数形式	5.12	.512（0可以省略，但必须有小数点 ）

​			科学计数法表示形式	5.12e2

```java
double num1 = 2.7;
double num2 = 8.1 / 3;
System.out.println(num1); // 2.7
System.out.println(num2); // 接近2.7的一个小数，而不是2.7	2.6999999999999997

// 当对运算结果是小数的进行相等判断时，需要特别注意
// 应该是以两个数差值的绝对值在某个精度范围内进行判断
// 如果是两个直接赋值或者查询得到的小数，是可以使用“==”进行相等判断的
if(num1 == num2){
    System.out.println("相等1")；
}
if(Math.abs(num1 - num2) < 0.000001){
    System.out.println("相等2")；
}
```



### 布尔型：存放true/false

​	boolean[1]

​	注：

​		Java中不能用0或者非0的整数替代false和true

### 字符型：存放单个字符,可以存放汉字

​	char[2]

​	注：

​		Java中还允许使用转义字符‘\’将其后的字符转变为特殊字符型常量	‘\n’表示换行符

​		在Java中，char的本质是一个整数，在输出时，默认输出是unicode码对应的字符	[unicode编码转换](http://tool.chinaz.com/Tools/unicode.aspx)

​		char类型可以进行运算，相当于一个整数，因为他都对应有Unicode编码

#### ASCII编码表

​	一个字节表示

​	一共128个字符

​	实际上一个字节可以表示256个字符，只用了128个

#### Unicode编码表

​	固定大小的编码

​	使用两个字节来表示字符

​	最多编码是65536个字符

​	好处：

​		将世界上所有的符号都纳入其中，每一个符号都给予一个独一无二的编码，使用Unicode没有乱码的问题

​	缺点

​		字母和汉字统一都是占用两个字节，这样浪费空间

#### utf-8

​	互联网上使用最广的一种Unicode的实现方式

​	大小可变的编码，可以使用1-6个字节表示一个符号，根据不同的符号而变化字节的长度

​	字母使用1个字节，汉字使用3个字节

#### gbk

​	可以表示汉字

​	范围广，字母使用1个字节，汉字使用2个字节

#### gb2312

​	可以表示汉字

​	gb2312 < gbk

#### big5码

​	繁体中文，台湾，香港

## 引用数据类型

### 类（class）

### 接口（interface）

### 数组[]

## 基本数据类型转换

### 自动类型转换

​	自动类型转换：当Java程序在进行赋值或者运算时，精度小的类型自动转换为精度大的数据类型

​	数据类型按精度（容量）大小排序为

​		char<int<long<float<double

​		byte<short<int<long<float<double

​	有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算

​	当精度（容量）大的数据类型赋值给精度（容量）小的数据类型时会报错，反之则会进行自动类型转换

​	（byte，short）和char之间不会相互自动转换，byte不超范围的情况下可以直接赋值

​	byte、short、char三者可以计算，在计算时首先转换为int类型

```java
    byte b = 16;
    short s = 14;
    short t = s + b;// 错误，s和b进行运算时首先转化为int，int类型的变量不能直接转换成						// short
```

​	boolean不参与转换

​	自动提升原则：表达式结果的类型自动提升为操作数中最大的类型

### 强制类型转换

​	自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型

​	使用时要加上强制类型转换符（），但可能造成精度降低或者溢出

​	当进行数据的大小从大到小，就需要使用到强制转换

​	强转符号只针对与于最近的操作数有效，往往会使用小括号提升优先级

​	char类型可以保存int的常量值，但不能保存int'的变量值，需要强转

​	byte和short类型在进行运算时，当作int类型处理

### 基本数据类型和String类型的转换

​	基本数据类型转换成String类型

​		基本数据类型的值+“”

​	String类型转基本数据类型

​		通过基本数据类型的包装类调用parseXX方法即可

```java
    Integer.parseInt("123");
    Double.parseDouble("123.1");
    Float.parseFloat("123.45");
    Short.parseShort("12");
    Long.parseLong("12345");
    Boolean.parseBoolean("true");
    Byte.parseByte("12");
```

​	把字符串转换成为字符 --> 含义是指把字符串的第一个字符得到

```java
    String s = "123";
    System.out.println(s.charAt(0));// 将s字符串的第一个字符返回	'1'
```

​	注：

​		在将String类型转换成基本数据类型时，要确保String类型能够转换成有效的数据（不能将英文字符串转换成一个整数）

​		如果格式不正确，就会抛出异常，程序就会终止

​		在“+”后面允许断行输出

```java
System.out.println("lalalalal" + "lalalalal" + "lalalalal" +
						"lalalalal" + "lalalalal" + "lalalalal");
```



# Java API文档

## API

Application Programming Interface	应用程序编程接口

Java提供的基本编程接口：Java提供的类和相关方法

[中文在线文档](https://www.matools.com/)



# 运算符

## %	取模（取余）

%的本质	a % b = a - a / b * b

```java
System.out.println(10 % 3);		//	1
System.out.println(-10 % 3);	//	-1
System.out.println(10 % -3);	//	1
System.out.println(-10 % -3);	//	-1
```



## i++ 和 ++i

```java
int a = 1;
a = a++;
System.out.println(a);//	1

int b = 1;
b = ++b;
System.out.println(b);//	2
```



## instanceof	检查是否是类的对象



关系运算符组成的表达式叫关系表达式



^	逻辑异或	a^b,当a和b不同时，则结果为true，否则为false



## &逻辑与和&&短路与的区别

​	&逻辑与		不管第一个条件是否为false，第二个条件都要判断，效率低

​	&&短路与	如果第一个条件为false，则第二个条件不会判断，最终结果为false，效率高

​	实际开发中基本使用短路与，效率较高



## |逻辑或和||短路或的区别

​	|逻辑或			不管第一个条件是否为true，第二个条件都要判断，效率低

​	||短路或			如果第一个条件为true，则第二个条件不会判断，最终结果为true，效率高

​	实际开发中基本使用短路或，效率较高



```java
boolean x = true;
boolean y = false;
short z = 46;
if((z++ == 46) && (y = true)) z++;	// 注意y = true 的最终运算结果还是true，他是先把true赋给了y，然后y作为关系表达式
if((x = false) || (++z == 49)) z++;
System.out.println("z=" + z);
```



## 复合赋值运算符会进行类型转换

```java
byte b = 3;
b += 2;	//	等价于 b = (byte)(b + 2)
b++;	//	等价于 b = (byte)(b + 1)
```



## 三元运算符

​	条件表达式？表达式1：表达式2；

​	注：

​		表达式1和表达式2要为可以赋值给接受变量的类型（或可以自动转换）



## 运算符优先级

​	只有单目运算符、赋值运算符是从右向左运算的



# 标识符

## 命名规则：

​		由26个英文字母大小写，0-9，_或$组成

​		数字不可以开头

​		不可以使用关键字和保留字，但能包含关键字和保留字

​			保留字：现有Java版本尚未使用，但是以后的版本可能会作为关键字使用

​		Java中严格区分大小写，长度没有限制

​		标识符不能包含空格



## 命名规范：

​		包名：多单词组成时所有的字母都小写

​		类名、接口名：多单词组成时，所有单词的首字母大写

​		变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写

​		常量名：所有字母都大写，多单词时每个单词用下划线连接

​		

# 键盘输入语句

```java
import java.util.Scanner;// 表示导入java.util下的Scanner类
public class Input{
	public static void main(String[] args){
		Scanner scanner = new Scanner(System.in);
		System.out.println("请输入用户名");
		String name = scanner.next();//	当程序执行到此处，会等待用户输入
        char gender = scanner.next().charAt(0);//接收字符
	}
}
```



# 进制

​	二进制		以0b或者0B开头

​	十进制

​	八进制		以数字0开头

​	十六进制	以0x或者0X开头	a-f不区分大小写



# 位运算符

按位与&			两位全为1，结果为1，否则为0

按位或|			两位有一个为1，结果为1，否则为0

按位异或^		两位一个为0一个为1，结果为1，否则为0

按位取反~		0->1，1->0

算术左移<<		符号位不变，低位补0

算术右移>>		低位溢出，符号位不变，并用符号位补溢出的高位

​	>>>				逻辑右移（无符号右移），低位溢出，高位补0

​	特别说明：没有 <<< 符号

```java
public class Input{
	public static void main(String[] args){
		int a = 1 >> 2;//向右移动两位
		int b = -1 >> 2;
		int c = 2 << 2
		int d = -1 << 2;
		int e = 3 >>> 2;
		System.out.println("a=" + a);// 0
		System.out.println("b=" + b);// -1
		System.out.println("c=" + c);// 8
		System.out.println("d=" + d);// -4
		System.out.println("e=" + e);// 0
	}
}
```



# 原码、补码、反码

​	对于有符号的而言

​		二进制的最高位是符号位：0表示正数，1表示负数

​		正数的原码、反码、补码都一样

​		负数的反码=它的原码符号位不变，其他位取反

​		负数的补码=它的反码+1，负数的反码=它的补码-1

​		0的反码、补码都是0

​		Java没有无符号数（Java中的数都是有符号的）

​		在计算机运算的时候，都是以补码的方式来运算的

​		当看运算结果时，要看原码



# switch分支结构

## 基本语法

switch（表达式）{

​	// 在Java中只要有值返回就是表达式

​	case	常量1：

​	语句块1；

​	break;

​	case	常量2：

​	语句块2；

​	break;

​	···

​	default:

​	default语句块；

​	break；

}

```java
import java.util.Scanner;
public class switch1{
	public static void main(String[] args){
		System.out.println("请输入a,b,c,d,e,f,g中任意一个字符");
		Scanner scanner = new Scanner(System.in);
		char input = scanner.next().charAt(0);
		switch(input){
			case 'a':
			System.out.println("星期一");
			break;
			case 'b':
			System.out.println("星期二");
			break;
			case 'c':
			System.out.println("星期三");
			break;
			case 'd':
			System.out.println("星期四");
			break;
			case 'e':
			System.out.println("星期五");
			break;
			case 'f':
			System.out.println("星期六");
			break;
			case 'g':
			System.out.println("星期日");
			break;
			default:
			System.out.println("输入有误，请重新输入！");
		}
	}
}
```

注意：

​	表达式数据类型，应该和case后面的常量类型一致，或者是可以自动转换成可以相互比较的类型

​	switch（表达式）中表达式的返回值必须是：（byte,short,int,char,enum,String）

​	case子句的值只能是常量或者常量表达式，不能是变量

​	default子句是可选的，当没有匹配的case时，执行default

​	break语句用来在执行完一个case分支后使程序跳出switch语句块；如果没有写break语句，程序会顺序执行到switch结尾

```java
import java.util.Scanner;
public class SwitchExercise2{
	public static void main(String[] args){
		System.out.println("请输入成绩");
		Scanner scanner = new Scanner(System.in);
		double input = scanner.nextDouble();
		if(input <= 100 && input >=0 ){
			switch((int)input / 60){
				case 0:
				System.out.println("不合格");
				break;
				default:
				System.out.println("合格");				
			}
	    }else{
	    	System.out.println("输入有误，请重新输入！");
	    }
	}
}
```



```java
import java.util.Scanner;
public class SwitchExercise3{
	public static void main(String[] args){
		System.out.println("请输入一个月份");
		Scanner scanner = new Scanner(System.in);
		int input = scanner.nextInt();
		if(input > 0 && input < 13){
			switch(input){
				case 12:
				case 1:
				case 2:
				System.out.println("冬季");
				break;
				case 3:
				case 4:
				case 5:
				System.out.println("春季");
				break;
				case 6:
				case 7:
				case 8:
				System.out.println("夏季");
				break;
				default:
				System.out.println("秋季");
			}
	    }else{
	    	System.out.println("输入有误，请重新输入！");
	    }
	}
}
```



# switch和if的比较

​	如果判断的具体数值不多，并且符合byte，short，int，enum，char，String这6种类型，虽然两个语句都可以使用，建议使用switch语句

​	其他情况：对区间判断，对结果为boolean类型判断，使用if，if的使用范围更广



# for循环控制

​	for（循环变量初始化；循环条件；循环变量迭代）{

​		循环操作（语句）；

​	}

​	四要素：

​		循环变量初始化

​		循环条件

​		循环操作

​		循环变量迭代

​	如果循环操作（语句）只有一条语句，可以省略{}，建议不要省略

​	说明：

​		循环条件是返回一个布尔值的表达式

​		for（；循环条件；）中的初始化和变量迭代可以写到其他地方，但是两边的分号不能省略

​			将初始化写在外面可以扩大初始化变量的作用域

​		循环初始值可以有多条初始化语句，但要求类型一样，并且中间用逗号隔开，循环变量迭代也可以有多条变量迭代语句，中间用逗号隔开

​		

```java
for(;;){

}
```



# while循环

## 基本语法

while(循环条件){

​	循环体（语句）；

​	循环变量迭代；

}



# do ...while循环控制

## 基本语法

循环变量初始化

do{

​	循环体（语句）；

​	循环变量迭代；

}while（循环条件）；

​	说明：
​		先执行，再判断，也就是说，一定会至少执行一次

​		最后有一个分号



# Math.random()

​	返回带正号的double值，该值大于等于0.0，且小于1.0（可以取到0，但取不到1）

​	(int)(Math.random()*100)+1



# break

break语句出现在多层嵌套的语句块中时，可以通过标签指明要终止的是哪一层语句块

标签的基本使用

label1:{

label2:{

label3:{

​			break label2;

​		}

​	}

}

说明：

​	break可以指定退出哪层

​	标签名由程序员自己指定

​	break后面指定到哪个label就退出到哪里

​	在实际开发中尽量不要使用label，会导致可读性变差

​	如果没有指定label，默认退出最近的循环体



# 数组

数组可以存放多个同一类型的数据，数组也是一种数据类型，是引用数据类型

## 数组的使用

### 初始化

数组的声明

​	数据类型 数组名[] or 数据类型[] 数组名

创建数组

​	动态初始化：

​		数据类型 数组名[] = new 数据类型[大小]

​		先声明数组，再new分配空间（声明的时候并没有分配存储空间）： 数组名 = new 数据类型[大小]

​	静态初始化：

​		数据类型 数组名[] = {元素值，元素值。。。}

数组的引用

​	数组名[下标/索引]

​	数组的下标从0开始

说明

​	数组是多个相同类型数据的组合，实现对这些数据的统一管理

​	数组中的元素可以是任何数据类型，包括基本类型和引用类型，但是不能混用

​	数组创建后，如果没有赋值，有默认值

​		

| int     | 0      |
| ------- | ------ |
| short   | 0      |
| byte    | 0      |
| long    | 0      |
| float   | 0.0    |
| double  | 0.0    |
| char    | \u0000 |
| boolean | false  |
| Stirng  | null   |

​	使用数组的步骤：

​		1、声明数组并开辟空间

​		2、给数组各个元素赋值

​		3、使用数组

​	数组的下标是从0开始的

​	数组的下标必须在指定范围内使用，否则会报：下标越界异常

​	数组术语引用类型，数组型数据是对象（Object）

## 数组的赋值机制

​	值拷贝：基本数据类型赋值，这个值就是具体的数据，而且相互不影响

​	地址拷贝（引用拷贝）：数组在默认情况下是引用传递，赋的值是地址

# 排序

排序是指将多个数据，依指定的顺序进行排列的过程

## 排序的分类

内部排序

​	指将需要处理的所有数据都加载到内部存储器中进行排序。包括：交换式排序法、选择式排序法、插入式排序法

外部排序法

​	数据量过大，无法全部加载到内存中，需要借助外部存储进行排序。包括：合并排序法和直接合并排序法

## 冒泡排序法（bubble sorting）

通过对待排序序列从后向前（从下标较大的元素开始），一次比较相邻元素的值，若发现逆序则交换，使值较大的元素逐渐从前移向后部



# 查找

在Java中，常用的查找有两种:

​	顺序查找

​	二分查找



# 二维数组

二维数组元素的个数： arr.length

二维数组中一维数组元素的个数：arr[i].length

二维数组的每个元素是一维数组，所以如果需要得到每个一维数组的值，还需要再次遍历

## 二维数组的使用

动态初始化

```java
第一种
	类型[][] 数组名 = new 类型[大小][大小]
第二种
    先声明：类型 数组名[][];
	再定义（开辟空间）：数组名 = new 类型[大小][大小]
    赋值（有默认值）
第三种
    int[][] arr = new int[3][];// 创建二维数组，但是只是确定一维数组的个数，但是每个一维数组并没有开辟空间
第四种
    静态初始化：类型 数组名[][] = {{值1，值2...},{值1，值2...},{值1，值2...}}
			或者 类型[][] 数组名 = {{值1，值2...},{值1，值2...},{值1，值2...}}
```

### 说明

​	一维数组的声明方式有

​		int[] x	或者	int x[]

​	二维数组的声明方式有

```
int[][] y	或者	int[] y[]	或者	int y[][]
```

​	二维数组实际上是由多个一维数组组成的，他的各个一维数组的长度可以相同，也可以不同



```
String数组定义的两种形式
String[] strs = {"a","b","c"}
String strs[] = new String[]{"a","b","c"}
```



# 类与对象

## 类和对象的区别和联系

​	类是抽象的，概念的，代表一类事物

​	对象是具体的，实际的，代表一个具体的事物

​	类是对象的模板，对象是类的一个个体，对应一个实例



## 字符串存放在方法区中的常量池中



## 属性/成员变量

​	成员变量=属性=field/字段	（成员变量是用来表示属性的）

​	属性是类的一个组成部分，一般是基本数据类型，也可以是引用数据类型（对象，数组）

​	属性的定义语法和变量相同	访问修饰符 属性类型 属性名;

​			四种访问修饰符	public protected,默认,private

​	属性的定义类型可以为任意类型，包括基本类型或引用类型

​	属性如果不赋值，有默认值，规则和数组一样

| int     | 0      |
| ------- | ------ |
| short   | 0      |
| byte    | 0      |
| long    | 0      |
| float   | 0.0    |
| double  | 0.0    |
| char    | \u0000 |
| boolean | false  |
| Stirng  | null   |

## 创建对象

​	1、先声明，再创建

​	2、直接创建

## 类和对象的内存分配机制

Java内存结构分析

​	栈				一般存放基本数据类型（局部变量）

​	堆				存放对象

​	方法区		常量池（常量，比如字符串），类加载信息

Java创建对象的流程简单分析

​	1、先加载类信息（属性和方法信息，只会加载一次）

​	2、在堆中分配空间，进行默认初始化把地址赋给对象引用

​	3、进行指定属性的初始化

## 成员方法

### 方法调用

方法调用的过程

​	1、当程序执行到方法时，就会开辟一个独立的空间（栈空间）

​	2、当方法执行完毕，或执行到return语句时，就会返回到调用方法的地方

​	3、返回后继续执行方法后面的代码

注意事项

​	同一个类中的方法直接调用即可

​	跨类中的方法需要通过对象名调用

​	跨类的方法调用和方法的访问修饰符相关

### 成员方法的好处

​	提高代码的复用性

​	可以将实现的细节封装起来，然后供其他用户来调用即可

### 成员方法的定义

public 返回数据类型 方法名 （形式参数列表...）{// 方法体

​	语句；

​	return 返回值；

}

​	参数列表							表示成员方法的输入

​	数据类型（返回类型）	表示成员方法的输出，void表示没有返回值

​	方法主体							表示为了实现某一功能的代码块

​	return语句						不是必须的

### 说明

​	访问修饰符

​			作用是控制方法使用的范围

​			如果不写，则为默认访问

​	返回数据类型

​			一个方法最多有一个返回值（如果返回多个结果，可以返回数组）

​			返回类型可以为任意类型，包含基本类型或者引用类型

​			如果方法要求有返回数据类型，则方法体中最后的执行语句必须为return值；而且要求返回值类型必须和return的值类型一致或者				兼容

​			如果方法是void，则方法体中可以没有return语句，或者只写return；

​	方法名

​			遵循驼峰命名法

​			最好见名知意，表达出该功能的意思即可

​	形式参数列表

​			一个方法可以有0个参数，也可以有多个参数，中间用逗号隔开

​			参数类型可以为任意类型，包含基本类型或引用类型

​			调用带参数的方法时，一定对应着参数列表传入相同类型或者兼容类型

​			方法定义的参数称为形式参数，方法调用时的参数称为实际参数

​			形式参数和实际参数的类型要一致或者兼容、个数、顺序必须一致

​	方法体

​			完成功能的具体语句，可以为输入、输出、变量、运算、分支、循环、方法调用，但里面不能再定义方法（方法不能嵌套定义）

### 成员方法的传参机制

​	对于基本数据类型，传递的是值（值拷贝），形参的任何改变不影响实参

​	引用类型传递的是地址（传递也是值，但是值是地址），可以通过形参影响实参

## 方法的递归调用

​	递归就是方法自己调用自己，每次调用时传入不同的变量

​	执行一个方法时，就创建一个新的受保护的独立空间（栈空间）

​	方法的局部变量是独立的，不会相互影响

​	如果方法中使用的是引用类型的变量，就会共享该引用类型的数据

​	递归必须向退出递归的条件逼近，否则就是无限递归，出现StackOverflowError

​	当一个方法执行完毕，或者遇到return，就会返回，遵守谁调用，就将结果返回给谁，同时当方法执行完毕或者返回时，该方法也就执行完毕



# 方法重载

Java中允许同一个类中，多个同名方法的存在，但要求形参列表不一致

重载的好处

​	减轻了起名的麻烦

​	减轻了记名的麻烦

说明

​	方法名

​		必须相同

​	参数列表

​		必须不同（形参类型或个数或顺序，至少有一种不同，形参名无要求）

​	返回类型

​		无要求



# 可变参数

Java种允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法，可以通过可变参数实现

基本语法

​	访问修饰符 返回类型 方法名(数据类型... 形参名){



​	}

## 说明

可变参数的实参可以是0个或者任意多个

可变参数的实参可以是数组

可变参数的本质就是数组

可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后

一个形参列表中只能出现一个可变参数



# 作用域

## 基本使用

在Java编程种，主要的变量就是属性（成员变量）和局部变量（一般指在成员方法中定义的变量）

Java种作用域的分类

​	全局变量	即属性，作用域为整个类

​	局部变量	除了属性之外的其它变量，作用域为定义它的代码块中

全局变量（属性）可以不赋值，直接使用，因为有默认值

局部变量必须赋值之后才能使用，因为没有默认值

## 说明

​	属性和局部变量可以重名，访问时遵循就近原则

​	在同一个作用域中，比如在同一个成员方法中，两个局部变量不能重名

​	属性生命周期较长，伴随着对象的创建而创建，伴随着对象的死亡而死亡

​	局部变量生命周期较短，伴随着它的代码块的执行而创建，伴随着代码块的结束而死亡，即在一次方法调用过程中

​	作用域不同

​			全局变量	可以被本类使用，或其它类使用（可以通过对象调用）

​			局部变量	只能在本类中对应的方法中使用

​	修饰符不同

​			全局变量/属性	可以加修饰符

​			局部变量			不可以加修饰符



# 构造方法/构造器

构造方法又叫构造器（constructor），是类的一种特殊的方法，它的主要作用是完成对新对象的初始化

[修饰符列表] 方法名(形参列表){

​		方法体;

}

## 说明

​	构造器的修饰符可以默认，也可以是其他的

​	构造器没有返回值

​	构造方法名/构造器名和类名必须一致

​	参数列表和成员方法一样的规则

​	一个类可以定义多个不同的构造器，即构造器重载

​	构造器是完成对象的初始化，并不是创建对象

​	在创建对象时，系统自动地调用该类的构造方法

​	如果程序员没有定义构造器，系统会自动给类生成一个默认无参构造器（也叫默认构造器）

​	一旦定义了自己的构造器，默认的构造器就覆盖了，就不能再使用默认的无参构造器，除非显式地定义一下

## 特点

​	方法名和类名相同

​	没有返回值

​	在创建对象时，系统会自动调用该类的构造器完成对对象的初始化

## 对象创建流程分析

​	加载类信息，只会加载一次

​	在堆中分配空间（地址）

​	完成对象的初始化

​				默认初始化（给属性赋默认值）

​				显式初始化（如果在定义属性时同时赋值，则在此时进行赋值）

​				构造器的初始化

​	把对象在堆中的地址返回给对象名（对象引用）

# this关键字

this关键字可以用来访问本类的属性、方法、构造器

this用来区分当前类的属性和局部变量

访问成员方法的语法

​			this.方法名(参数列表)		注意只能在构造器中使用（即只能在构造器中访问另一个构造器，并且只能放在构造器的第一条语句）

this不能在类定义的外部使用，只能在类定义的方法中使用



# 匿名对象

new 类名（）

匿名对象只能使用一次，使用后就不能再使用了



# IDEA

在idea中，当run一个文件时，会先编译成.class，再运行

## IDEA常用快捷键

（settings->keymap）

删除当前行

​				默认是	ctrl + Y

​				可自行配置	ctrl + d

复制当前行

​				可自行配置	ctrl + alt + 向下光标

补全代码

​				alt + /

添加注释和取消注释

​				ctrl + /

导入该行所需要的类

​				先配置auto import，然后使用	alt + enter

快速格式化代码

​				ctrl + alt + L

快速运行程序

​				默认是	shift + F10

​				可自行配置	alt + R

生成构造器等

​				alt + insert

查看一个类的层级关系

​				ctrl + H

将光标放在一个方法上，输入ctrl + b，可以定位到哪个类的方法

自动分配变量名

​				通过在后面	.var

## 模板

(file->settings->editor->Live templates)

# 包

包的本质就是创建不同的文件夹来保存类文件

## 作用

区分相同名字的类

当类很多时，可以很好的管理类

控制访问范围

## 基本语法

package com.royt

package	关键字,表示打包

com.royt	表示包名

## 命名规则

只能包含数字、字母、下划线、小圆点

不能用数字开头

不能是关键字或保留字

## 命名规范

一般是	小写字母+小圆点

一般是	com.公司名.项目名.业务模块名

## Java中常用的包

java.lang.*	lang包是基本包，默认引入，不需要再引入

java.util.*	util包，系统提供的工具包、工具类

java.net.*	网络包，网络开发

java.aet.*	做Java的界面开发，GUI

## 引入包

import 包

引入包的目的只要是要使用该包下面的类

建议

​				需要使用哪个类，就导入哪个类即可，不建议使用*导入

## 说明

package的作用是声明当前类所在的包，需要放在类（或者文件）的最上面，一个类中最多只有一句package

import指令位置放在package的下面。在类定义前面，可以有多句且没有顺序要求

# 访问修饰符

Java提供四种访问控制修饰符号控制方法和属性（成员变量）的访问权限（范围）

​				公开级别				用public修饰，对外公开

​				受保护级别			用protected修饰，对子类和同一个包中的类公开

​				默认级别				没有修饰符号，向同一个包中的类公开

​				私有级别				用private修饰，只有类本身可以访问，不对外公开

| 访问级别 | 访问修饰符 | 同类 | 同包 | 子类 | 不同包 |
| -------- | ---------- | ---- | ---- | ---- | ------ |
| 公开     | public     | √    | √    | √    | √      |
| 受保护   | protected  | √    | √    | √    | ×      |
| 默认     | 没有修饰符 | √    | √    | ×    | ×      |
| 私有     | private    | √    | ×    | ×    | ×      |

## 说明

修饰符可以用来修饰类中的属性、成员方法以及类

只有默认和public才能修饰类，并且遵循上述访问权限的特点

成员方法的访问规则和属性完全一样



# 封装(encapsulation)

封装九十八抽象出来的数据【属性】和对数据的操作【方法】封装在一起，数据被保护在内部，程序的其他部分只有通过被授权的操作【方法】，才能对数据进行操作

## 封装的好处

隐藏实现细节

可以对数据进行验证，保证安全合理

## 封装的实现步骤

1、将属性进行私有化private【不能直接修改属性】

2、提供一个公共的(public)set方法，用于对属性判断并赋值

```java
public void setXxxx(类型 参数名){// Xxx表示某个属性
	// 加入数据验证的业务逻辑
	属性 = 参数名;
}
```

3、提供一个公共的get方法，用于获取属性的值

```java
public XX getXxx(){// 权限判断
	return xx;
}
```



# 继承(extends)

继承可以解决代码的复用，当多个类存在相同的属性（变量）和方法时，可以从这些类中抽象出父类，在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，只需要通过extends来声明继承父类的方法即可

## 基本语法

class 子类 extends 父类{

}

子类会自动拥有父类定义的属性和方法

父类又叫做超类、基类

子类又叫做派生类

## 继承的好处

代码的复用性提高了

代码的扩展性和维护性提高了

## 说明

​	1、子类继承了所有的属性和方法，但是私有属性和方法不能在子类中直接访问，要通过公共的方法去访问

​	2、

​	3、

​	4、

​	5、

​	6、

​	7、

​	8、

​	9、

​	10、



















































































































# 快捷键

## 编辑类

ctrl + J	合并选中的多行代码为一行	可以将多行格式的CSS属性合并为一行

ctrl + shift + D	复制光标所在整行，插入到下一行

tab	向右缩进

shift + tab	向左缩进

ctrl + k + k	从光标处开始删除代码至行尾

ctrl + shift + k	删除整行

ctrl + /	注释整行

ctrl + shift + /	注释多行

ctrl + k + u	转换大小写

ctrl + k + l	转换小写

ctrl + z	撤销



# X

## javap指令	反编译

​	使用	javap *.class

## hashCode()方法

​	由Object类定义的hashCode()方法确实会针对不同的对象返回不同的整数（这一般是通过将该对象的内部地址转换成一个整数来实现的，但是Java编程语言不需要这种实现技巧）

## Random

​	public int nextInt(int n)	返回一个伪随机数，他是取自此随机数生成器序列、在0（包括）和指定值（不包括）之间均匀分布的int值

```
Random r = new Random();
num = r.nextInt(3);// 产生一个[0,2)的随机数
```

## Math.abs()

​	求绝对值（不需要导包，可以直接使用）

## Arrays.sort()

(import java .util.Arrays)

数组自动排序

## String.length()

返回字符串的长度





















































# 附录

## 字母表的顺序和逆序输出

```java
public class Homework4{
	public static void main(String[] args){
		for(char c = 'a' ; c <= 'z';c++){
			System.out.print(c + " ");
		}
		for(char c = 'Z' ; c >= 'A';c--){
			System.out.print(c + " ");
		}
	}
}
```

## 双指针for循环

```java
public class ArrayTest5{
	public static void main(String[] args){
		int[] arr = {11,22,33,44,55,66};
		for(int i = 0 ;i < arr.length / 2 ; i++){
			int temp = arr[i];
			arr[i] = arr[arr.length - 1 - i];
			arr[arr.length - 1 - i] = temp;
		}
		for(int i = 0 ;i < arr.length ; i++){
			System.out.println(arr[i]);
		}
		int[] rearr = new int[arr.length];
		for(int i = 0 ; i < arr.length ; i++){
			rearr[i] = arr[arr.length - 1 - i];
		}
		for(int i = 0 ;i < rearr.length ; i++){
			System.out.println(rearr[i]);
		}
        
        
		int[] rearr2 = new int[arr.length];
		for(int i = arr.length - 1,j = 0;i >= 0;i--,j++){// 增加一个循环变量
			rearr2[j] = arr[i];
		}
		arr = rearr2;// 此时arr原来的数据空间就没有变量引用，会被当作垃圾销毁掉
		for(int i = 0 ;i < arr.length ; i++){
			System.out.println(arr[i]);
		}
	}
}
```

## 数组添加

实现动态的给数组添加元素效果，实现对数组的扩容

​	原始数组使用静态分配

​	增加的元素直接放在数组最后

​	用户可以通过如下方法来决定是否继续添加，添加成功，是否继续

```java
import java.util.Scanner;
public class ArrayTest6{
	public static void main(String[] args){
		Scanner scanner = new Scanner(System.in);
		int[] arr = {1,2,3};
		System.out.println("====原始数组====");
		for(int i = 0 ; i < arr.length ; i++ ){
			System.out.print(arr[i] + " ");
		}
		while(true){
			System.out.println("是否继续添加元素？（y/n）");
			char ans = scanner.next().charAt(0);
			if(ans == 'y'){
				System.out.println("请输入想要添加的元素：");
				int element = scanner.nextInt();
				int[] newArr = new int[arr.length + 1];
				for(int i = 0 ; i < arr.length ; i++){
					newArr[i] = arr[i];
				}
				newArr[newArr.length - 1] = element;
				arr = newArr;
				System.out.println("====添加成功，新数组====");
				for(int i = 0 ; i < arr.length ; i++ ){
					System.out.print(arr[i] + " ");
				}
				System.out.println();
			}else{
				break;
			}
		}
	}
}
```

## 数组缩减

```java
import java.util.Scanner;
public class ArrayTest7{
	public static void main(String[] args){
		Scanner scanner = new Scanner(System.in);
		int[] arr = {1,2,3,4,5};
		for(int i = 0 ; i < arr.length ; i++){
			System.out.print(arr[i] + "\t");
		} 
		System.out.println();
		while(true){
		    System.out.println("是否要继续缩减？（y/n）");
		    char ans = scanner.next().charAt(0);
		    if(ans == 'y' && arr.length > 1){
		    	int[] newArr = new int[arr.length - 1];
		    	for(int i = 0 ; i < newArr.length ; i++){
					newArr[i] = arr[i];
				} 
				arr = newArr;
				System.out.println("===缩减成功，新数组====");
				for(int i = 0 ; i < arr.length ; i++ ){
					System.out.print(arr[i] + " ");
				}
		    }else if (arr.length == 1){
		    	System.out.println("提示：不能再缩减了");
		    	break;
		    }else{
		    	break;
		    }
	    }
	}
}
```

## 冒泡排序

```java
public class BubbleSorting{
	public static void main(String[] args){
		int[] arr = {24,69,80,57,13};
		int temp= 0;
		for(int i = 0 ; i < arr.length - 1 ; i++ ){// 外层循环	轮
			for(int j = 0 ; j < arr.length - i - 1 ; j++ ){// 内层循环次数	每一轮的比较次数
			    if(arr[j] > arr[j + 1]){
			    	temp = arr[j];
			    	arr[j] = arr[j + 1];
			    	arr[j + 1] = temp;
			    }
		    }
		}
		System.out.println("===冒泡排序后，新数组====");
		for(int i = 0 ; i < arr.length ; i++ ){
			System.out.print(arr[i] + " ");
		}
	}
}
```

## 顺序查找

```java
import java.util.Scanner;
public class SeqSearch{
	public static void main(String[] args){
		String[] arr = {"白眉鹰王","金毛狮王","紫衫龙王","青翼蝠王"};
		Scanner scanner = new Scanner(System.in);
		System.out.println("请输入你想要查找的名称：");
		String ans = scanner.next();
		int order = -1;
		for(int i = 1 ; i < arr.length ; i++){
			if(arr[i].equals(ans)){
				order = i;
				break;
			}
		}
		if(order == -1){
			System.out.println("抱歉，并没有找到对应的名称");
		}else{
			System.out.println("找到名称为" + ans +
			 "的元素，其下标为" + order);
		}
	}
}
```

## 初始化长度不相等的二维数组

```java
public class TDA{
	public static void main(String[] args){
		int[][] arr = new int[3][];// 创建二维数组，但是只是确定一维数组的个数，但是每个一维数组并没有开辟空间
		for(int i = 0 ; i < arr.length ; i++ ){
			arr[i] = new int[i + 1];
			for(int j = 0 ; j < arr[i].length ; j++ ){
				arr[i][j] = i + 1;
			}
		}
		for(int i = 0 ; i < arr.length ; i++ ){
			for(int j = 0 ; j < arr[i].length ; j++){
				System.out.print(arr[i][j] + "\t");
			}
			System.out.println();
		}
	}
}

输出结果为：
1
2       2
3       3       3
```

## 杨辉三角

```java
public class YangHui{
	public static void main(String[] args){
		int rows = 10;
		int[][] tri = new int[rows][];
		for(int i = 0 ; i < tri.length ; i++){
			tri[i] = new int[i + 1];
			for(int j = 0 ; j < tri[i].length ; j++){// 在此条件下已经包含了第一行为1的情况，不用再单独讨论
				if(j == 0 || j == tri[i].length - 1 ){
				    tri[i][j] = 1;
			    }else{
			    	tri[i][j] = tri[i - 1][j - 1] + tri[i - 1][j];
			    }
			}
		}
		for(int i = 0 ; i < tri.length ; i++ ){
			for(int j = 0 ; j < tri[i].length ; j++){
				System.out.print(tri[i][j] + "\t");
			}
			System.out.println();
		}
	}
}

输出结果为：
1
1       1
1       2       1
1       3       3       1
1       4       6       4       1
1       5       10      10      5       1
1       6       15      20      15      6       1
1       7       21      35      35      21      7       1
1       8       28      56      70      56      28      8       1
1       9       36      84      126     126     84      36      9       1
```

## 数组插入元素之后，原顺序不变

```java
public class Homework7{
	public static void main(String[] args){
		int[] arr = {10,12,45,90};
		System.out.println("====插入元素前====");
		for(int i = 0 ; i < arr.length ; i ++){
			System.out.println(arr[i] + "\t");
		}
		int num = 23;
		int flag = -1;
		for(int i = 0 ; i < arr.length ; i ++){
			if(arr[i] > num){
				flag = i;
				break;
			}
		}
		if (flag == -1){// 如果遍历完之后，没有发现比num小的元素，则它应该被添加到数组末尾
			flag = arr.length;
		} 
		int[] newArr = new int[arr.length + 1];
		// for(int i = 0 ; i < newArr.length ; i ++){
		// 	if(i < flag){
		// 		newArr[i] = arr[i];
		// 	}else if(i == flag){
		// 		newArr[i] = num;
		// 	}else{
		// 		newArr[i] = arr[i - 1];
		// 	}
		// }
		for(int i = 0,j = 0; i < newArr.length ; i ++){
			if(i != flag){
				newArr[i] = arr[j];
				j++;
			}else{
				newArr[i] = num;
			}
		}
		arr = newArr;
		System.out.println("====插入元素后====");
		for(int i = 0 ; i < arr.length ; i ++){
			System.out.println(arr[i] + "\t");
		}
	}
}
```

## 斐波那契数列

```java
public class FBNQ{
	public static void main(String[] args){
		FB fbnq = new FB();
		int res = fbnq.fb(5);
		System.out.println(res);
	}
}
class FB{
	public int fb(int n){
		if(n >= 1){
			if(n == 1 || n == 2){
				return 1;
			}else{
				return fb(n - 1) + fb(n - 2);
			}
		}else{
			System.out.println("input error!!!");
			return -1;
		}
	}
}
```

## 猴子吃桃

每天吃一半，再多吃一个，第十天只剩1个（第十天没吃）

```java
public class Monkey{
	public static void main(String[] args){
		Peach p = new Peach();
		System.out.println(p.peach(1));
	}
}

class Peach{
	public int peach(int day){
		if(day == 10){
			return 1;
		}else if(day >= 1 && day <= 9){
			return 2 * (peach( day + 1 ) + 1);
		}else{
			System.out.println("input error!!!");
			return -1;
		}
	}
}
```

## 迷宫

```java
public class MiGong{
	public static void main(String[] args){
		int[][] map = new int[8][7];
		for(int i = 0 ; i < map.length ; i++){
			for(int j = 0 ; j < map[0].length ; j ++){
				if(i == 0 || i == map.length -1){
					map[i][j] = 1;
				}else{
					if(j == 0 || j == map[i].length - 1){
						map[i][j] = 1;
					}
				}
	        }// 0 表示可以走，1 表示障碍物
		}
		map[3][1] = 1;
		map[3][2] = 1;
		System.out.println("======当前地图======");
		for(int i = 0 ; i < map.length ; i++){
			for(int j = 0 ; j < map[0].length ; j ++){
			    System.out.print(map[i][j] + " ");		
			}
			System.out.println();
		}
		Tool tool = new Tool();
		tool.findWay(map,1,1);
		System.out.println("======完成地图======");
		for(int i = 0 ; i < map.length ; i++){
			for(int j = 0 ; j < map[0].length ; j ++){
			    System.out.print(map[i][j] + " ");		
			}
			System.out.println();
		}

		
	}
}

class Tool{
	// 0 表示可以走
	// 1 表示障碍物
	// 2 表示可以走
	// 3 表示走过，但是是死路走不通
	// 当map[6][5] = 2 就说明找到通路，就可以结束，否则就继续找
	public boolean findWay(int[][] map,int i,int j){
		if(map[6][5] == 2){// 说明已经找到
			return true;
		}else{
			if(map[i][j] == 0){
				map[i][j] = 2;
				if(findWay(map , i + 1 , j)){
					return true;
				}else if(findWay(map , i , j + 1)){
					return true;
				}else if(findWay(map , i - 1 , j)){
					return true;
				}else if(findWay(map , i , j - 1)){
					return true;
				}else{
					map[i][j] = 3;
					return false;
				}
			}else{
				return false;
			}
			
		}
		
	}
}

运行结果：
======当前地图======
1 1 1 1 1 1 1
1 0 0 0 0 0 1
1 0 0 0 0 0 1
1 1 1 0 0 0 1
1 0 0 0 0 0 1
1 0 0 0 0 0 1
1 0 0 0 0 0 1
1 1 1 1 1 1 1
======完成地图======
1 1 1 1 1 1 1
1 2 0 0 0 0 1
1 2 2 2 0 0 1
1 1 1 2 0 0 1
1 0 0 2 0 0 1
1 0 0 2 0 0 1
1 0 0 2 2 2 1
1 1 1 1 1 1 1
```

## 汉诺塔

```java
public class HanoiTower{
	public static void main(String[] args){
		Tower tower = new Tower();
		char a = 'a';
		char b = 'b';
		char c = 'c';
		tower.move(3,a,b,c);
	}
}

class Tower{
	public void move(int num, char a,char b, char c){
		if ( num == 1){
			System.out.println(a + "---->" + c);
		}else{
			move(num - 1,a,c,b);
			System.out.println(a + "---->" + c);
			move(num - 1,b,a,c);
		}
	}
}
```

## 可变参数

```java
public class VarParameterExercise{
	public static void main(String[] args){
		Methods methods = new Methods();
		methods.showSocre("向明",11.1,22.2,33.3,44.4);
	}
}

class Methods{
	public void showSocre(String name,double... scores){
		double total = 0;
		for(int i = 0 ; i < scores.length ; i++){
			total += scores[i];
		}
		System.out.println("姓名：" + name + "，总分：" + total);
        // return "姓名：" + name + "，总分：" + total;
	}
}
```

## 求一个double数组的最大值

```java
public class Homework9{
	public static void main(String[] args){
		double[] num = new double[]{};
		Tool tool = new Tool();
		Double max = tool.max(num);
		if(max != null){
		    System.out.println("max = " + max);
	    }else{
	    	System.out.println("数组不能为空！");
	    }
	}
}

class Tool{// 先考虑业务，再考虑代码的健壮性
	public Double max(double[] num){
		if(num.length > 0){
			double max = num[0];
			for(int i = 1 ; i < num.length ; i++ ){
				if(num[i] > max){
					max = num[i];
				}
			}
			return max;
	    }else{
	    	return null;
	    }
	}
}
```

## 查找字符串中的某个元素

```java
public class Homework10{
	public static void main(String[] args){
		String[] strings = {"aaa","bbb","ccc"};
		Tool tool = new Tool();
		String s = "aaa";
		int index = tool.find(strings,s);
		if(index == -1){
		    System.out.println("该字符串数组中不存在元素" + s);
	    }else{
	    	System.out.println("元素"+ s + "在该字符串数组中的索引为" + index);
	    }
	}
}

class Tool{
	public int find(String[] strings,String s){
		for(int i = 0 ; i < strings.length ; i++ ){
			if(s.equals(strings[i])){
				return i;
			}
		}
		return -1;
	}
}
```

## 更改书的价格

```java
public class Homework11{
	public static void main(String[] args){
		Book book1 = new Book("lala",44);
		System.out.println(book1.name + " price = " + book1.price);
		book1.updatePrice();
		System.out.println(book1.name + " price = " + book1.price);
		Book book2 = new Book("hehe",101);
		System.out.println(book2.name + " price = " + book2.price);
		book2.updatePrice();
		System.out.println(book2.name + " price = " + book2.price);
		Book book3 = new Book("haha",151);
		System.out.println(book3.name + " price = " + book3.price);
		book3.updatePrice();
		System.out.println(book3.name + " price = " + book3.price);
	} 
}

class Book{
	String name;
	double price;
	public Book(){

	}
	public Book(String name , double price){
		this.name = name;
		this.price = price;
	}
	public void updatePrice(){
		if(this.price > 150){
			this.price = 150;
		}else if(this.price > 100){
			this.price = 100;
		}
	}
}
```

复制数组

```jaba
public class Homework12{
	public static void main(String[] args){
		int[] arr = {1,2,3,4,5,6,7,8,9};
		System.out.println("=====原数组=====");
		for(int i = 0 ; i < arr.length ; i++){
			System.out.print(arr[i] + "\t");
		}
		System.out.println();
		Tool tool = new Tool();
		int[] newArr = tool.copyArr(arr);
		System.out.println("=====新数组=====");
		for(int i = 0 ; i < newArr.length ; i++){
			System.out.print(newArr[i] + "\t");
		}
	}
}

class Tool{
	public int[] copyArr(int[] arr){
		int[] newArr = new int[arr.length];
		for(int i = 0 ; i < arr.length ; i++){
			newArr[i] = arr[i];
		}
		return newArr;
	}
	public double[] copyArr(double[] arr){
		double[] newArr = new double[arr.length];
		for(int i = 0 ; i < arr.length ; i++){
			newArr[i] = arr[i];
		}
		return newArr;
	}
	public String[] copyArr(String[] arr){
		String[] newArr = new String[arr.length];
		for(int i = 0 ; i < arr.length ; i++){
			newArr[i] = arr[i];
		}
		return newArr;
	}
}
```

根据圆的半径求周长和面积

```java
public class Homework14{
	public static void main(String[] args){
		Cale cale1 = new Cale(4,2);
		System.out.println(cale1.sum());
		System.out.println(cale1.reduce());
		System.out.println(cale1.mul());
		if(cale1.devide() != null){
		    System.out.println(cale1.devide());
    	}
        Cale cale2 = new Cale(4,0);
		System.out.println(cale2.sum());
		System.out.println(cale2.reduce());
		System.out.println(cale2.mul());
		if(cale2.devide() != null){
		    System.out.println(cale2.devide());
    	}
	}
}

class Cale{
	Integer num1;
	Integer num2;
	public Cale(){

	}
	public Cale(Integer num1 , Integer num2){
		this.num1 = num1;
		this.num2 = num2;
	}
	public Integer sum (){
		return num1 + num2;
	}
	public Integer reduce(){
		return num1 - num2;
	}
	public Integer mul(){
		return num1 * num2;
	}
	public Integer devide(){
		if(num2 == 0){
			System.out.println("被除数不能为0");
			return null;
		}else{
			return num1 / num2;
		}
	}
}
```

