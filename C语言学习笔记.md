# C语言学习笔记

## 1、数据类型

- 整数
  - int
  - printf("%d",...)
  - scanf("%d",...)

- 带小数点的数
  - double
  - printf("%f",...)
  - scanf("%f",...)

## 2、”嵌入式赋值“

```c
int a = 6;
int b;
int c = 1+(b=a);
```

- 不利于阅读
- 容易产生错误

## 3、复合赋值

- total +=(sum+100)/2;
  - total = total + (sum + 100 )/2;

- total *= sum+ 12;
  - **total = total*(sum+ 12);**

- total /=12 + 6;

  - **total = total/(12+6）；**

    ### 前缀后缀

    | 表达式  | 运算       | 表达式的值     |
    | ------- | ---------- | -------------- |
    | count++ | 给count加1 | count原来的值  |
    | ++count | 给count加1 | count加1后的值 |
    | count-- | 给count减1 | count原来的值  |
    | --count | 给count减1 | count减1后的值 |

    

    ```c
    #include <stdio.h>
    int main()
    {
    	int a;
    	a = 10;
    	printf("a++=%d\n", a++);
    	printf("a=%d\n", a);
    
    	printf("++a=%d\n", ++a);
    	printf("a=%d\n", a);
    return 0;
    }
    ```

    *a++的结果还是a的值，这一步之后a再进行+1运算*

    *++a是先运算a+1再输出*

    ---

    ## 4、基本数据类型
    
    ![](https://img.mukewang.com/547fd0af0001b55b06300091.jpg)
    
    ## 5、常用格式化符
    
    ![](https://img.mukewang.com/54856b620001e2ad04880099.jpg)

```c
printf("%d\n",100); //整型常量
printf("%f\n",3.14); //实型常量
printf("%c\n",'A'); //字符常量
printf("I love imooc!"); //字符型常量
在C语言中，可以用一个标识符来表示一个常量，称之为符号常量。符号常量在使用之前必须先定义，其一般形式为：
    #define 标识符 常量值
```

## 4、判断

``` c
if(条件成立){...
        }
```

**注意：表示相等关系要用“==”**

*一段找零代码，有点小问题*

```c
//初始化
	float price = 0;
	float bill = 0;
	//读入金额和票面
	printf("请输入金额：");
	scanf_s("%f", &price);
	printf("请输入票面：");
	scanf_s("%f", &bill);
	//计算找零
	if (bill >= price) {
		printf("应该找您：%f", bill - price);
	}
	
	else {
		printf("您的余额不足\n");
	}
```

## 5、swich-case

- 控制表达式只能是整数型的结果
- 常量可以是常数，也可以是常数计算的表达式

```c
swich(控制表达式){
    case 常量：
        语句
        break;
    case 常量：
        语句
        break;
    default :
    语句
        break;
}
```

**记得在每个case后面加上break**

## 6、强制类型转换

强制类型转换是通过定义类型转换运算来实现的。其一般形式为：

 **(数据类型) (表达式)** 

其作用是把表达式的运算结果强制转换成类型说明符所表示的类型，例如：

![](https://img.mukewang.com/5492b8960001b56b03870081.jpg)

输入结果：

![](https://img.mukewang.com/54801a8b0001ffe700830051.jpg)

PS:表达式一定要加括号，变量名不加
