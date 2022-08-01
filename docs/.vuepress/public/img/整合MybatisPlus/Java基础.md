## 一、面向对象概述

### 1.1 什么是面向对象？

**概述: 将事务高度抽象化的编程模式**
	将问题分解成一个一个步骤，对每个步骤进行相应的抽象，形成对象，通过不同对象之间的调用，组合解决问题。
	就是说，在进行面向对象进行编程的时候，要把属性、行为等封装成对象，然后基于这些对象及对象的能力进行业务逻辑的实现。
	比如：想要造一辆车，上来要先把车的各种属性定义出来，然后抽象成一个 Car 类。

### 1.2 面向对象的三大基本特征

> 封装(Encapsulation)、继承(Inheritance)、多态(Polymorphism)

**封装(Encapsulation)：**

	所谓封装，也就是把客观事物封装成抽象的类，并且类可以把自己的数据和方法只让可
信的类或者对象操作，对不可信的进行信息隐藏。
	封装是面向对象的特征之一，是对象和类概念的主要特性。简单的说，一个类就是一个
封装了数据以及操作这些数据的代码的逻辑实体。在一个对象内部，某些代码或某些数据可
以是私有的，不能被外界访问。通过这种方式，对象对内部数据提供了不同级别的保护，以
防止程序中无关的部分意外的改变或错误的使用了对象的私有部分。

**继承(Inheritance)：**

	继承是指这样一种能力：它可以使用现有类的所有功能，并在无需重新编写原来的类的
情况下对这些功能进行扩展。
	通过继承创建的新类称为“子类”或“派生类”，被继承的类称为“基类”、“父类”
或“超类”。继承的过程，就是从一般到特殊的过程。
	继承概念的实现方式有二类：实现继承与接口继承。实现继承是指直接使用基类的属性
和方法而无需额外编码的能力；接口继承是指仅使用属性和方法的名称、但是子类必须提供
实现的能力。

**多态(Polymorphism)：**

	所谓多态就是指一个类实例的相同方法在不同情形有不同表现形式。多态机制使具有不
同内部结构的对象可以共享相同的外部接口。这意味着，虽然针对不同对象的具体操作不同，
但通过一个公共的类，它们（那些操作）可以通过相同的方式予以调用。

	最常见的多态就是将子类传入父类参数中，运行时调用父类方法时通过传入的子类决定
具体的内部结构或行为。	

## 二、类与对象

### 2.1 类与对象关系

`一个程序就是一个世界，有很多事务对象[属性、行为]`

- **对象**：对象是类的一个实例（**对象不是找个女朋友**），有状态和行为。例如，一条狗是一个对象，它的状态有：颜色、名字、品种；行为有：摇尾巴、叫、吃等。
- **类**：类是一个模板，它描述一类对象的行为和状态。

下图中**汽车**为**类（class）**，而具体的每辆车为该**汽车**类的**对象（object）**，对象包含了汽车的颜色、品牌、名称等。

 ![img](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-44.png)

### 2.2 类的定义

	类是对象的抽象，它用于描述一组对象的`共同特征和行为`，例如人都有姓名、年龄、性别等特征，还有学习、工作、购物等下行为。以面向对象的编程思想，就可以将某一类中共同的特征和行为`封装`起来，把共同特征作为类的`属性（也叫成员变量）`把共同行为作为类的`方法（也叫成员方法）`。

1、类的定义格式

	Java中的类是通过class关键字来定义的，其语法格式如下：

```java
[修饰符]class 类名[extends 父类名] [implements 接口名] {
	//类体，包括类的成员变量和成员方法
}
```

::: tip 解析

	上述语法格式中，class前面的修饰符可以是public，也可以不写（默认）；class之后是定义的类名，类名首字母要大写，并且其命名要符合标识符的命名规则；extends和implements是可选项，均为Java中的关键字，`其中extends用于说明所定义的类继承于哪个父类，implements关键字用于说明当前实现了哪些接口。`后面大括号{ }中的内容是类体，即需要在类中编写的内容，它主要包括`类的成员变量和成员方法`。

:::

2、声明（定义）成员变量

	类的成员变量也称作`类的属性`，它主要用于描述对象的特征。例如，一个人的基本属性特征有姓名、年龄、职业、地址等信息，在类中要使用姓名、年龄等信息时，就需要将它们声明（定义）为成员变量。
	
	声明（定义）成员变量的语法格式如下：

```java
[修饰符] 数据类型 变量名 [=值];
```

::: tip 解析

	上述语法格式中，修饰符是可选项，用于指定`变量的访问权限`，其值可以为`public，private`等；数据类型可以为Java中的任意数据类型；变量名是变量的名称，必须符合标识符的命名规则，它可以赋予初始值，也可以不赋值。通常情况下，`将未赋值（没有被初始化）的变量成为声明变量，而赋值（初始值）的变量成为定义变量。`
	
	例如，姓名和年龄属性在类中的声明和定义方式如下：

```java
public String name;             //声明一个String类型的name
public int age = 20;            //定义一个int类型的age，并赋值为20
```

:::

3、声明（定义）成员方法

	成员方法也被称为方法，它主要用于描述对象的行为。一个人的基本行为特征有吃饭、睡觉、运动等，这些行为在Java类中，就可以定义成方法。
	
	定义一个方法的语法格式如下：

```java
[修饰符][返回值类型] 方法名([参数类型 参数名1,参数类型 参数名2,.....]){
	//方法体
	·
	·
	return 返回值;    //当方法的返回类型为void时，return及其返回值可以省略
}
```

::: tip 解析

	上面语法格式中，[ ]中的内容表示可选，各部分具体说明如下：
	
	①修饰符：方法的修饰符比较多，有对访问权限进行限定的（如public，protected，private），有静态修饰符static，还有最终修饰符final等。
	
	②返回值类型：用于限定方法返回值的数据类型，如果不需要返回，可以使用void关键字
	
	③参数类型：用于限定调用方法时传入参数的数据类型。
	
	④参数名：是一个变量，用于接收调用方法时传入的数据。
	
	⑤return关键字：用于结束方法以及返回方法指定类型的值，当方法的返回值类型为void时，return及其返回值可以省略。
	
	⑥返回值：被return语句返回的值，该值会返回给调用者。

:::

	案例：Person.java

![1651029465097](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-45.png)

::: danger 脚下留心

	在Java中，定义在类中的变量被称为成员变量，定义在方法中的变量叫做`局部变量`。如果在某一个地方中定义的局部变量与成员变量同名，这种情况是允许的，此时方法中通过变量访问到的是局部变量，而并非成员变量，实例代码如下：

```ajva
public class Person {
    int age = 10 ;              //类中定义的变量被称作为成员变量
    //定义speak()方法
    void speak(){
        int age = 30;           //方法内部的变量被称为局部变量
        System.out.println("我今年"+age+"岁了！");
    }
}
```

	上面代码中，speak( )方法中的打印语句所访问的变量age，就是局部变量，也就是说，当有另外一个程序来调用speak( )方法时，输出的值是30，而非10。

“成员变量” 和“局部变量” 的区别：

**1. 类中位置不同：**
           成员变量（类中、方法外）
           局部变量（方法内部或方法声明上）
**2. 内存中位置不同：**
          成员变量（堆内存）
          局部变量（栈内存）
**3. 生命周期不同：**
          成员变量（随着对象的存在而存在，随着对象的消失而消失）
          局部变量（随着方法的调用而存在，随着方法的调用完毕而消失）
**4. 初始化值不同：**
          成员变量（有默认初始化值）
          局部变量（没有默认初始化值，必须先定义，赋值才能使用）

:::

### 2.3 对象的创建与使用

#### 2.3.1 概念

	应用程序想要完成具体的功能，仅有类是远远不够的，还需要根据类创建实例对象。在Java程序中可以使用new关键字来创建对象，具体语法格式如下：

```java
类名 对象名称 = new 类名();
```

例如：创建Person类的实例对象代码如下：

```java
Person p = new Person();
```

	上面的代码中，“new Person（）”用于创建 Person 类的一个实例对象，“Person p”則是声明了一个Person 类型的变量 p。中间的等号用于将 Person 对象在内存中的地址赋值给变量 p,这样变量p便持有了对象的引用，为了便于描述，本书接下米的童节通常会梅变量引用的对象简称为 p对象。在肉存中交量p和对象之间的引用关系如图所示。

![1651062696908](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-46.png)

	由图可知，在创建 Person 对象时，程序会占用两块内存区城，分别是栈内存和堆内存。其中 Person 类型的变最p被存放在栈内存中，它是一个引用，会指向真正的对象；通过 new Person(创建的对象则放在堆内存中,这才是真正的对象。

::: tip 小提示

	Java 将内存分为两种，即`栈内存和堆内存`。其中栈内存用于存放基本类型的变量和对象的引用变量(如Person p)，堆内存用于存放由new创建的对象和数组。

- 栈:保存局部变量的值：包括1.基本数据类型的值。2.保存类的实例，即堆区对象的引用（指针）。3.保存加载方法时的帧。
- 堆：用来存放动态产生的数据，比如new出来的对象。注意创建出来的对象只包含属于各自的成员变量，并不包括成员方法。因为同一个类拥有各自的成员变量，存储在堆中的不同位置，但是同一个类不同实例的他们共享该类的方法，并不是每创建一个对象就把成员方法复制一次。

 ![这里写图片描述](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-47.png) 

:::

	在创建 Person 对象后,可以通过对象的引用来访间对象所有的成员，具体格式如下:

```java
对象引用.对象成员
```

### 2.4 访问控制符

在Java中，针对类、成员方法和属性提供了4中级别访问，分别是private、default、protected、public。

> 1) 公开级别(public):用 public 修饰,对外公开 
>
> 2) 受保护级别(protected):用 protected 修饰,对子类和同一个包中的类公开 
>
> 3) 默认级别(default):没有修饰符号,向同一个包的类公开. 
>
> 4) 私有级别(private):用 private 修饰,只有类本身可以访问,不对外公开.

![1651064088241](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-48.png)



## 三、类的封装

### 3.1 概念

	`封装就是把抽象出的数据[属性]和对数据的操作[方法]封装在一起，数据被保护在内部，程序的其他部分只有通过被授权的操作[方法]，才能对数据进行操作`例如：一台计算机内部极其复杂，有主板、CPU、硬盘和内存， 而一般用户不需要了解它的内部细节，不需要知道主板的型号、CPU 主频、硬盘和内存的大小，于是计算机制造商将用机箱把计算机封装起来，对外提供了一些接口，如鼠标、键盘和显示器等，这样当用户使用计算机就非常方便。 

### 3.2 封装的特点

- 只能通过规定的方法访问数据。
- 隐藏类的实例细节，方便修改和实现

### 3.3 实现封装的步骤

	① 修改属性的可见性来限制对属性的访问，一般设为 private。
	
	② 为每个属性创建一对赋值（setter）方法和取值（getter）方法，一般设为 public，用于属性的读写。
	
	③ 在赋值和取值方法中，加入属性控制语句（对属性值的合法性进行判断）。

### 3.4 如何实现封装

	具体实现过程是：在定义一个类的时候，将类中的属性私有化，即使用`private`关键字来修饰，私有属性只能在它所在类中被访问，如果外界想要访问私有属性，需要提供一些使用public修饰的公有方法，其中包括获取属性值的getXxx（）方法和设置属性值的setXxx（）方法。

```java
public class Employee {
        private String name; // 姓名
        private int age; // 年龄
        private String phone; // 联系电话
        private String address; // 家庭住址

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public int getAge() {
            return age;
        }

        public void setAge(int age) {
            // 对年龄进行限制
            if (age < 18 || age > 40) {
                System.out.println("年龄必须在18到40之间！");
                this.age = 20; // 默认年龄
            } else {
                this.age = age;
            }
        }

        public String getPhone() {
            return phone;
        }

        public void setPhone(String phone) {
            this.phone = phone;
        }

        public String getAddress() {
            return address;
        }

        public void setAddress(String address) {
            this.address = address;
        }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", phone='" + phone + '\'' +
                ", address='" + address + '\'' +
                '}';
    }
}
```

::: tip 解析

 如上述代

![1651238063449](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-55.png)

::: danger 提示

当一个类的属性（成员变量）名与访问该属性的方法参数名相同时，则需要使用this关键字来访问类中的属性，以区分类的属性和方法中的参数。



```java
public class Person {
  public Person(){
      System.out.println("无参构造方法被调用了。。。。。");
  }
  public Person(int age){
      this();							//调用无参构造方法
      System.out.println("有参构造方法被调用了。。。。。");
  }

    public static void main(String[] args) {
        Person person=new Person(20);	//实例化Person对象
    }
}
```

结果:

![1651240029538](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-56.png)

::: danger  使用this调用类的构造方法时，应注意以下几点

1. 只能在构造方法中使用this调用其他的构造方法，不能在成员方法中使用。
2. 在构造方法中，使用this调用构造方法的语句必须是该方法的第一条执行语句，且只能出现一次。下面的写法是错误的。

```java
public Person(int age){
      System.out.println("有参构造方法被调用了。。。。。");
      this();				//调用无参构造方法
  }
```

		在上述代码中，由于调用的this（ ）不是构造方法的第一条执行语句，所有会报“Constructor call must be the first statement in a constructor(调用构造函数必须是构造函数的第一条语句)”的错误信息。
	
	3. 不能在一个类的两个构造方法中使用this互相调用。下面额写法是错误的

```java
public class Person {
  public Person(){
      this(18);//调用有参构造方法
      System.out.println("无参构造方法被调用了。。。。。");
  }
  public Person(int age){
      this();//调用无参构造方法
      System.out.println("有参构造方法被调用了。。。。。");
  }
}  
```

在上述代码中，无参构造方法和有参构造方法分别使用了this关键字对方法进行了互相调用，此时在编译时，将会报出“Recursive constructor invocation Person( )(递归调用构造函数Person（）)”的错误信息

:::

## 七、static关键字

::: info static作用

 在类中，使用 static 修饰符修饰的属性（成员变量）称为`静态变量`，也可以称为`类变量`，常量称为`静态常量`，方法称为`静态方法或类方法`，它们统称为`静态成员`，归整个类所有。 

 静态成员不依赖于类的特定实例，被类的所有实例共享，就是说 static 修饰的方法或者变量不需要依赖于对象来进行访问，只要这个类被加载，Java虚拟机就可以根据类名找到它们。 

 调用静态成员的语法形式如下： 

```
类名.静态成员
```

:::

::: danger 注意

- static 修饰的**成员变量和方法**，`从属于类`。
- 普通变量和方法从`属于对象`。
- **静态方法不能调用非静态成员**，编译会报错。

:::

### 静态变量

类的成员变量可以分为以下两种：

1. 静态变量（或称为类变量），指被 static 修饰的成员变量。
2. 实例变量，指没有被 static 修饰的成员变量。

静态变量与实例变量的区别如下:

1）静态变量

- 运行时，Java虚拟机只为静态变量分配一次内存，在加载类的过程中完成静态变量的内存分配。
- 在类的内部，可以在任何方法内直接访问静态变量。
- 在其它类中，可以通过类名访问该类中的静态变量。

2）实例变量

- 每创建一个实例，Java虚拟机就会为实例变量分配一次内存。
- 在类的内部，可以在非静态方法中直接访问实例变量
- 在本类的静态方法或其他类中则需要通过类的实例对象进行访问。

 静态变量在类中的作用如下： 

- **静态变量可以被类的所有实例共享**，因此静态变量可以作为实例之间的共享数据，增加实例之间的交互性。
- 如果类的所有实例都包含一个相同的常量属性，则可以把这个属性定义为静态常量类型，从而节省内存空间。例如， 在类中定义一个静态常量 PI。 

```java
public static double PI = 3.14159256;
```

**例 1**

创建一个带静态变量的类，然后在 main() 方法中访问该变量并输出结果。

```java
public class StaticVar {
    public static String str1 = "Hello";
    public static void main(String[] args) {
        String str2 = "World!";
        // 直接访问str1
        String accessVar1 = StaticVar.str1 +str2;
        System.out.println("第1次访问静态变量，结果为："+accessVar1);
        // 通过类名访问str1
        String accessVar2 = StaticVar.str1 + str2;
        System.out.println("第2次访问静态变量，结果为："+accessVar2);
        // 通过对象svt1访问str1
        StaticVar svt1 = new StaticVar();
        svt1.str1 = svt1.str1+str2;
        String accessVar3 = svt1.str1;
        System.out.println("第3次访向静态变量，结果为："+accessVar3);
        // 通过对象svt2访问str1
        StaticVar svt2 = new StaticVar();
        String accessVar4 = svt2.str1+str2;
        System.out.println("第4次访问静态变量，结果为："+accessVar4);
    }
}
```

 运行该程序后的结果如下所示。 

![1651404814485](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-57.png)

 从运行结果可以看出，在类中定义静态的属性**（成员变量），在 main() 方法中可以直接访问，也可以通过类名访问，还可以通过类的实例对象来访问。**

::: danger 注意

静态变量是被`多个实例所共享`的。 

:::

### 静态方法

与成员变量类似，成员方法也可以分为以下两种:

1. 静态方法（或称为类方法），指被static修饰的成员方法。
2. 实例方法，指没有被static修饰的成员方法。

静态方法与实例方法的区别：

- 静态方法不需要通过它的所属的对象实例就可以被调用，因此在静态方法中不能使用this关键字，也不能直接访问所属类的实例变量和实例方法，但是可以直接访问所属类的静态变量和静态方法。另外和this关键字一样，super关键字也与类的特定实例相关，所以在静态方法中也不能使用super关键字
- 在实例方法中可以直接访问所属类的静态变量、静态方法、实例变量和实例方法。

**例2**

创建一个带静态变量的类添加几个静态方法对静态变量的值进行修改，然后再main（）方法中调用静态方法并输出结果。

```java
public class StaticMethod {
    public static int count = 1;    //定义静态变量count
    public int method1(){
        // 实例方法method1
        StaticMethod.count++;    // 访问静态变量count并赋值
        System.out.println("在静态方法 method1()中的count="+ StaticMethod.count);
        return StaticMethod.count;
    }
    public static int method2(){
        // 静态方法method2
        StaticMethod.count += StaticMethod.count;// 访问静态变量count并赋值
        System.out.println("在静态方法 method2()中的 count="+ StaticMethod.count);
        return StaticMethod.count;
    }
    public static void PrintCount() {
        // 静态方法PrintCount
        StaticMethod.count += 2;
        System.out.println("在静态方法 PrintCount()中的 count="+ StaticMethod.count);    // 打印count
    }
    public static void main(String[] args) {
        StaticMethod sft = new StaticMethod();
        // 通过实例对象调用实例方法
        System.out.println("method1() 方法返回值 intro1="+sft.method1());
        // 直接调用静态方法
        System.out.println("method2() 方法返回值 intro1="+ StaticMethod.method2());
        // 通过类名调用静态方法，打印 count
        StaticMethod.PrintCount();
    }
}
```

 运行该程序后的结果如下所示。 

![1651407715834](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-58.png)

 在该程序中，静态变量 count 作为实例之间的共享数据，因此在不同的方法中调用 count，值是不一样的。从该程序中可以看出，在静态方法 method1() 和 PrintCount() 中是不可以调用非静态方法 method1() 的，而在 method1() 方法中可以调用静态方法 method2() 和 PrintCount()。 

 **在访问非静态方法时，需要通过实例对象来访问，而在访问静态方法时，可以直接访问，也可以通过类名来访问，还可以通过实例化对象来访问。** 

### 静态代码块

 静态代码块指 Java 类中的 `static{ } 代码块`，主要用于初始化类，为类的静态变量赋初始值，提升程序性能。 

静态代码块的特点如下：

- 静态代码块类似于一个方法，但它不可以存在于任何方法体中。
- 静态代码块可以置于类中的任何地方，类中可以有多个静态初始化块。 
- Java 虚拟机在加载类时执行静态代码块，所以很多时候会将一些只需要进行一次的初始化操作都放在 static 代码块中进行。
- 如果类中包含多个静态代码块，则 Java 虚拟机将按它们在类中出现的顺序依次执行它们，每个静态代码块只会被执行一次。
- 静态代码块与静态方法一样，不能直接访问类的实例变量和实例方法，而需要通过类的实例对象来访问。

**例 3**

编写一个 Java 类，在类中定义一个静态变量，然后使用静态代码块修改静态变量的值。最后在 main() 方法中进行测试和输出。

```java
public class StaticCode {
    public static int count = 0;
    {
        StaticCode.count++;
        System.out.println("非静态代码块count="+ StaticCode.count);
    }
    static {
        StaticCode.count ++;
        System.out.println("静态代码块1 count="+ StaticCode.count);
    }
    static {
        StaticCode.count++;
        System.out.println("静态代码块2 count="+ StaticCode.count);
    }

    public static void main(String[] args) {
        System.out.println("*************** StaticCode1 执行 ***************");
        StaticCode staticCode1 = new StaticCode();
        System.out.println("*************** StaticCode2 执行 ***************");
        StaticCode staticCode2 = new StaticCode();
    }
}
```

 如上述示例，为了说明静态代码块只被执行一次，特地添加了非静态代码块作为对比，并在主方法中创建了两个类的实例对象。上述示例的执行结果为： 

![1651408340091](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-59.png)

 上述代码中 { } 代码块为非静态代码块，非静态代码块是在创建对象时自动执行的代码，不创建对象不执行该类的非静态代码块。代码域中定义的变量都是局部的，只有域中的代码可以调用。  

# 面向对象（下）

## 一、继承

### 1.1 继承的概念

::: info 继承介绍

	 继承是面向对象的三大特征之一。继承和现实生活中的“继承”的相似之处是保留一些父辈的特性，从而减少代码冗余，提高程序运行效率。 

:::

	Java 中的继承就是在已经存在类的基础上进行扩展，从而产生新的类。已经存在的类称为父类、基类或超类，而新产生的类称为子类或派生类。在子类中，不仅包含父类的属性和方法，还可以增加新的属性和方法。 
	
	在程序中，如果想声明一个类继承另一个类，需要使用`extends关键字`，其基本语法格式如下：

```java
[修饰符]class子类名 extends 父类名{
    //程序核心代码
}
```

	在上述语法格式中，类的修饰符是可选的，用来指定类的访问权限，可以使用public或者省略不写；子类名和父类名都是必选的，并且子类与父类之间要使用`extends关键字`来实现继承关系.

**例 1**

创建一个Animal类，定义一个dog类继承animal类

```java
class Animal{
    String name;            //声明name属性
    //定义动物的叫法
    void shout(){
        System.out.println("动物发出声音");
    }
}
class Dog extends Animal {
    public void printName() {
        System.out.println("name叫" + name);
    }
}
public class Example01 {
    public static void main(String[] args) {
            Dog dog=new Dog();
            dog.name="lizhou";
            dog.shout();
            dog.printName();
    }
}
```

运行结果：

![1651409743248](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-60.png)

上例中，Dao类通过extends关键字继承了Animal类，这样Dog类便是Animal类的子类。从运行结果可以看出，子类虽然没有声明name属性和shout（）方法，但却能访问这两个成员这就说明，子类在继承父类的时候，会自动拥有父类的公共成员

::: tip 实现类的继承，需要注意的一些问题

1. 在Java中，类只支持单继承，不允许多重继承，也就是说一个类只能有一个直接父类
2. 多个类可以继承同一个父类
3. 在Java中，多层继承是可以的，即一个类的父类可以再去继承另外的父类
4. 在Java中，子类和父类是一种概念，也就是说一个类是某个父类的同时，也可以是另一个类的子类。

:::

### 1.2 重写父类方法

	在继承关系中，子类会自动继承父类中公共的方法，但有时在子类中需要对继承的方法进行一些修改，即`对父类的方法进行重写`。需要注意的是，**子类中重写的方法需要和父类被重写的方法具有相同的方法名、参数列表以及返回值类型。**
	例4-1中，Dog类从Animal类继承了shout()方法，该方法在被调用时会打印“动物出叫声”，这显然不能描述一种动物的具体叫声，Dog类对象表示犬类，发出的叫声应该是“汪汪”。为了解决这个问题，可以在Dog类中重写父类Animal中的shout()方法，如下代码所示。

```java
class Animal{
    //定义动物的叫法
     void shout(){
        System.out.println("动物发出声音");
    }
}
class Dog extends Animal {
    @Override
    void shout() {
        System.out.println("汪汪。。。。。。");
    }

}
public class Example01 {
    public static void main(String[] args) {
            Dog dog=new Dog();
            dog.shout();
    }
}
```

结果：

![1651461714125](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-61.png)

上述代码中，定义了Dog类并且继承自Animal类。在子类Dog中定义了一个shout()方法对父类的方法进行重写。从运行结果可以看出，在调用Dog类对象的shout()方法时，只
会调用子类重写的方法，并不会调用父类的sout()方法。

::: danger 注意

子类重写父类方法时，不能使用比父类中被重写的方法更严格的访问权限。如父类中的方法访问权限是public,子类重写父类该方法的访问权限就不能是private。

:::

### 1.3 super关键字

从上述代码的运行结果可以看出，**当子类重写父类的方法后，子类对象将无法直接访回父类被重写的方法**。为了解决这个问题，在Java中专门提供了一个super关键字来访问父类的成员，例如访问交类的成员变量、成员方法和构造方法。下面分两种情况来学习super关键字的具体用法。
(1)使用sup心r关键字调用父类的成员变量和成员方法，具体格式如下：

```JAVA
super.成员变量
super.成员方法{[参数1,参数2....]}
```

接下来通过一个案例来学习如何使用super关键字调用父类的成员变量和成员方法，

```java
class Animal{
    String name="动物";
    //定义动物的叫法
     void shout(){
        System.out.println("动物发出声音");
    }
}
class Dog extends Animal {
    String name="犬类";

    @Override
    void shout() {
        super.shout();//访问父类的成员方法
    }
    //定义打印name的方法
    void printName(){
        System.out.println("name="+super.name);//访问父类的成员变量
    }

}
public class Example01 {
    public static void main(String[] args) {
            Dog dog=new Dog();   //创建一个dog对象
            dog.shout();         //调用dog对象重写的shout方法
            dog.printName();     //调用dog对象的printName（）方法
    }
}
```

结果：

![1651462207976](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-62.png)

	上述代码中，定义了一个Dog类继承Animal类，重写了Animal类的shout()方法并重新定义了子类的name属性。在子类Dog的shout()方法中使用“super..shout()”调用了父类
被重写的方法，在printName()方法中使用“super.name”访间父类的成员变量。从运行结果可以看出，子类通过super关键字成功地访问了父类成员方法和成员变量。
(2)使用super关键字调用父类的构造方法，具体格式如下：

```java
super({参数1,参数2.....})
```

案例：

```java
class Animal{
    public  Animal(String name){
        System.out.println("我是一只"+name);
    }
}
class Dog extends Animal {
    public Dog(){
        super("沙皮狗");//调用父类的有参构造方法
    }

}
public class Example01 {
    public static void main(String[] args) {
            Dog dog=new Dog();   //创建一个dog对象

    }
}
```

结果：

![1651462680197](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-63.png)

	根据前面所学的知识，在上述代码中在创建D0g类对象时一定会调用Dog类的构造方法，从运行结果可以看出，Dog类的构造方法被调用时，执行了内部的“super("沙皮狗“)”方法从面而调用了父类的有参构造方法。**需要注意的是，通过super调用父类构造方法的代码必须位于子类构造方法的第一行，并且只能出现一次，否则程序在编译期间就会报错**



### 1.4 Object类

	在Java中提供了一个Object类，它是所有类的父类，即每个类都直接或间接继自该类，因此Object类通常被称为超类，基类或根类。当定义一个类时，如果没有使用extends
关键字为这个类显式地指定父类，那么该类会默认继承Object类。

	Object类中常用的方法

![1651463378135](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-64.png)



#### 1.4.1 toString() 方法

 toString() 方法返回该对象的字符串，当程序输出一个对象或者把某个对象和字符串进行连接运算时，系统会自动调用该对象的 toString() 方法返回该对象的字符串表示。

Object 类的 toString() 方法返回“运行时类名@十六进制哈希码”格式的字符串，但很多类都重写了 Object 类的 toString() 方法，用于返回可以表述该对象信息的字符串。 

>  哈希码（hashCode），每个 Java 对象都有哈希码属性，哈希码可以用来标识对象，提高对象在集合操作中的执行效率。 

 先看以下代码： 

```java
class Demo {

}

public class ObjectDemo01 {
    public static void main(String[] args) {
        Demo d = new Demo(); // 实例化Demo对象
        System.out.println("不加toString()输出：" + d);
        System.out.println("加上toString()输出：" + d.toString());
    }
}
```

 输出结果为： 

![1651463628006](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-67.png)

 以上的程序是随机输出了一些地址信息，从程序的运行结果可以清楚的发现，**加和不加 toString() 的最终输出结果是一样的**，也就是说**对象输出时一定会调用 Object 类中的 toString() 方法打印内容**。所以利用此特性就可以通过 toString() 取得一些对象的信息，如下面代码。 

```java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    @Override
    public String toString(){
        return "姓名：" + name + "：年龄" + age;
    }

    public static void main(String[] args) {
        Person p = new Person("Java学习",20);
        System.out.println("对象信息"+p);
    }

}

```

 输出结果为： 

![1651463935247](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-65.png)

 程序中的 Person 类中重写了 Object 类中的 toString() 方法，这样直接输出对象时调用的是被子类重写过的 toString() 方法。 

#### 1.4.2 equals() 方法

 	在前面学习字符串比较时，曾经介绍过两种比较方法，分别是`==`运算符和 equals() 方法，`==`运算符是比较两个引用变量是否指向同一个实例，equals() 方法是比较两个对象的内容是否相等，通常字符串的比较只是关心内容是否相等。 

 其使用格式如下： 

```
boolean result = obj.equals(Object o);
```

其中，obj 表示要进行比较的一个对象，o 表示另一个对象。

**例 1**

	编写一个 Java 程序，实现用户登录的验证功能。要求用户从键盘输入登录用户名和密码，当用户输入的用户名等于 admin 并且密码也等于 admin 时，则表示该用户为合法用户，提示登录成功，否则提示用户名或者密码错误信息。
	在这里使用 equals() 方法将用户输入的字符串与保存 admin 的字符串对象进行比较，具体的代码如下：

```java
public class Test01 {
    // 验证用户名和密码
    public static boolean vavalidateLogin(String username,String password){
        boolean con = false;
        if (username.equals("admin")&&password.equals("admin")){// 比较两个 String 对象
            con = true;
        }else {
            con = false;
        }
        return con;
    }
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("------欢迎使用大数据管理平台------");
        System.out.println("用户名：");
        String username = input.next(); // 获取用户输入的用户名
        System.out.println("密码：");
        String password = input.next(); // 获取用户输入的密码
        boolean con = vavalidateLogin(username, password);
        if (con) {
            System.out.println("登录成功！");
        } else {
            System.out.println("用户名或密码有误！");
        }
    }
}
```

 上述代码在 validateLogin() 方法中又使用 equals() 方法将两个 String 类型的对象进行了比较，当 uname 对象与保存 admin 的 String 对象相同时，uname.equals("admin") 为 true；与此相同，当 upwd 对象与保存 admin 的 String 对象相同时，upwd.equals("admin") 为 true。当用户输入的用户名和密码都为 admin 时，表示该用户为合法用户，提示登录成功信息，否则提示用户名或密码有误的错误信息。

#### 1.4.3 getClass

`getClass( )方法返回对象所属的类，是一个Class对象`。通过Class对象可以获取该类的各种信息，包括类名、父类以及它所实现的接口的名字等。

**例二**

编写一个实例，演示如何对String类型调用getClass( )方法，然后输出父类以及实现的接口信息。具体实现代码如下：

```java
public class Test02 {
    public static void pringtClassInfo(Object obj){
        // 获取类名
        System.out.println("类名："+obj.getClass().getName());

        //获取父类名
        System.out.println("父类："+obj.getClass().getSuperclass().getName());
        System.out.println("实现的接口有：");

        //获取实现的接口并输出
        for (int i = 0;i<obj.getClass().getInterfaces().length;i++){
            System.out.println(obj.getClass().getInterfaces()[i]);
        }
    }
    public static void main(String[] args) {
        String obj = new String();
        pringtClassInfo(obj);
    }
}
```

 该程序的运行结果如下： 

![1652102509682](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-66.png)

## 二 final关键字

::: info

	final关键字可用于修饰类、变量和方法，它有“不可更改”或者“最终”的含义，因此被final修饰的类、变量和方法将具有以下特性：
	
	①final修饰的类不能被继承
	
	②final修饰的方法不能被子类重写
	
	③final修饰变量（成员变量和局部变量）是常量，只能赋值一次

:::

### 2.1 fianl关键字修

```java
final class SuperClass {
}
class SubClass extends SuperClass {    //编译错误
}
```

 因为 SuperClass 类是一个 final 类，而 SubClass 试图继承 SuperClass 类，这将会引起编译错误。 

### 2.2 final关键字修饰方法

	final修饰的方法不可被重写，如果出于某些原因，不希望子类重写父类的某个方法，则可以使用final修饰该方法
	
	Java提供的Object类里就有一个final方法getClass( ),因为java不希望任何类重写这个方法，所以使用final把这个方法密封起来。但对于该类提供的toString( )和equals( )方法，都允许子类重写，因此没有使用final修饰它们。

下面程序视图重写final方法，将会引起编译错误。

```java
public class FinalMethodTest {
    public final void test() {
    }
}
class Sub extends FinalMethodTest {
    // 下面方法定义将出现编译错误，不能重写final方法
    public void test() {
    }
}
```

上面程序中父类是FinalMethodTest，该类里定义test（）方法是一个final方法，如果其子类试图重写该方法，将会引起编译错误。

 对于一个 private 方法，因为它仅在当前类中可见，其子类无法访问该方法，所以子类无法重写该方法——如果子类中定义一个与父类 private 方法有相同方法名、相同形参列表、相同返回值类型的方法，也不是方法重写，只是重新定义了一个新方法。因此，即使使用 final 修饰一个 private 访问权限的方法，依然可以在其子类中定义与该方法具有相同方法名、相同形参列表、相同返回值类型的方法。 

 下面程序示范了如何在子类中“重写”父类的 private final 方法。 

```java
public class PrivateFinalMethodTest {
    private final void test() {
    }
}
class Sub extends PrivateFinalMethodTest {
    // 下面的方法定义不会出现问题
    public void test() {
    }
}
```

 上面程序没有任何问题，虽然子类和父类同样包含了同名的 void test() 方法，但子类并不是重写父类的方法，因此即使父类的 void test() 方法使用了 final 修饰，子类中依然可以定义 void test() 方法。

final 修饰的方法仅仅是**不能被重写，并不是不能被重载**，因此下面程序完全没有问题。 

```java
public class FinalOverload {
    // final 修饰的方法只是不能被重写，完全可以被重载
    public final void test(){}
    public final void test(String arg){}
}
```

### 2.3 final 修饰变量

final 修饰的变量即成为常量，只能赋值一次，但是 final 所修饰局部变量和成员变量有所不同。

1. final 修饰的局部变量必须使用之前被赋值一次才能使用。
2. final 修饰的成员变量在声明时没有赋值的叫“空白 final 变量”。空白 final 变量必须在构造方法或静态代码块中初始化。

::: tip 注意

 	final 修饰的变量不能被赋值这种说法是错误的，严格的说法是，final 修饰的变量不可被改变，一旦获得了初始值，该 final 变量的值就不能被重新赋值。 

:::

```java
public class FinalDemo {
    void doSomething() {
        // 没有在声明的同时赋值
        final int e;
        // 只能赋值一次
        e = 100;
        System.out.print(e);
        // 声明的同时赋值
        final int f = 200;
    }
    // 实例常量
    final int a = 5; // 直接赋值
    final int b; // 空白final变量
    // 静态常量
    final static int c = 12;// 直接赋值
    final static int d; // 空白final变量
    // 静态代码块
    static {
        // 初始化静态变量
        d = 32;
    }
    // 构造方法
    FinalDemo() {
        // 初始化实例变量
        b = 3;
        // 第二次赋值，会发生编译错误
        // b = 4;
    }
}
```

上述代码第 4 行和第 6 行是声明局部常量，其中第 4 行只是声明没有赋值，但必须在使用之前赋值（见代码第 6 行），其实局部常量最好在声明的同时初始化。代码第 13、14、16 和 17 行都声明成员常量。代码第 13 和 14 行是实例常量，如果是空白 final 变量（见代码第 14 行），则需要在构造方法中初始化（见代码第 27 行）。代码第 16 和 17 行是静态常量，如果是空白 final 变量（见代码第 17 行），则需要在静态代码块中初始化（见代码第 21 行）。
另外，无论是那种常量只能赋值一次，见代码第 29 行为 b 常量赋值，因为之前 b 已经赋值过一次，因此这里会发生编译错误。

**final 修饰基本类型变量和引用类型变量的区别**

当使用 final 修饰基本类型变量时，不能对基本类型变量重新赋值，因此基本类型变量不能被改变。 但对于引用类型变量而言，它保存的仅仅是一个引用，final 只保证这个引用类型变量所引用的地址不会改变，即一直引用同一个对象，但这个对象完全可以发生改变。
下面程序示范了 final 修饰数组和 Person 对象的情形。

```java
import java.util.Arrays;
class Person {
    private int age;
    public Person() {
    }
    // 有参数的构造器
    public Person(int age) {
        this.age = age;
    }
    // 省略age的setter和getter方法
    // age 的 setter 和 getter 方法
}
public class FinalReferenceTest {
    public static void main(String[] args) {
        // final修饰数组变量，iArr是一个引用变量
        final int[] iArr = { 5, 6, 12, 9 };
        System.out.println(Arrays.toString(iArr));
        // 对数组元素进行排序，合法
        Arrays.sort(iArr);
        System.out.println(Arrays.toString(iArr));
        // 对数组元素赋值，合法
        iArr[2] = -8;
        System.out.println(Arrays.toString(iArr));
        // 下面语句对iArr重新赋值,非法
        // iArr = null;
        // final修饰Person变量，p是一个引用变量
        final Person p = new Person(45);
        // 改变Person对象的age实例变量，合法
        p.setAge(23);
        System.out.println(p.getAge());
        // 下面语句对P重新赋值，非法
        // p = null;
    }
}
```

 从上面程序中可以看出，使用 final 修饰的引用类型变量不能被重新赋值，但可以改变引用类型变量所引用对象的内容。例如上面 iArr 变量所引用的数组对象，final 修饰后的 iArr 变量不能被重新赋值，但 iArr 所引用数组的数组元素可以被改变。与此类似的是，p 变量也使用了 final 修饰，表明 p 变量不能被重新赋值，但 p 变量所引用 Person 对象的成员变量的值可以被改变。

::: tip 注意

	在使用 final 声明变量时，要求全部的字母大写，如 SEX，这点在开发中是非常重要的。

:::

如果一个程序中的变量使用 public static final 声明，则此变量将称为全局变量，如下面的代码： 

```java
public static final String SEX= "女";
```

## 三、抽象类与接口 

### 3.1 抽象类

- 在Java中`abstract`是抽象的意思，可以修饰类、成员方法。
- `abstract`修饰类，这个类就是抽象类；修饰方法，这个方法就是抽象方法

语法格式如下：

```java
<abstract>class<class_name> {
    <abstract><type><method_name>(parameter-iist);
}
public abstract class Bank {
    public abstract void pay(double money2);
}
```

 **其中，abstract 表示该类或该方法是抽象的；class_name 表示抽象类的名称；method_name 表示抽象方法名称，parameter-list 表示方法参数列表。** 

::: tip 注意

如果一个方法使用`abstract`来修饰，则说明该方法是抽象方法，抽象方法只有声明没有实现。需要注意的是`bstract`关键字只能用于普通方法，不能用于`static(静态)方法`或者构造方法中。

:::

> 抽象方法有3个特征：
>
> 1. 抽象方法没有方法体
> 2. 抽象方法必须存在于抽象类中
> 3. 子类重写父类的时候，必须重写父类所有的抽象方法

::: tip 注意

 在使用 abstract 关键字修饰抽象方法时不能使用 private 修饰，因为抽象方法必须被子类重写，而如果使用了 private 声明，则子类是无法重写的。 

:::

### 3.2 定义和使用规则

1. 抽象类和抽象方法都要使用abstract关键字声明
2. 如果一个方法被声明为抽象的，那么这个类也必须声明为抽象的。而一个抽象类中，可以有0~n个抽象方法，以及0~n个具体方法
3. 抽象类不能实例化，也就是不能使用 new 关键字创建对象。

### 3.3 抽象的使用场景

- 抽象类可以理解为不完整的设计图，一般作为父类，让子类来继承
- 当父类知道子类一定要完成某些行为，但是每个子类该行为的实现不同，于是该父类就把该行为定义成抽象方法的形式，具体实现交由子类完成。

### 3.4 案例

 不同几何图形的面积计算公式是不同的，但是它们具有的特性是相同的，都具有长和宽这两个属性，也都具有面积计算的方法。那么可以定义一个抽象类，在该抽象类中含有两个属性（width 和 height）和一个抽象方法 area( )，具体步骤如下 

1）首先创建一个表示图形的抽象类Shape，代码如下所示：

```java
public abstract class Shape {
    private int width;  //几何图形的长

    private int height; //几何图形的宽

    public Shape(int width,int height){
        this.width = width;
        this.height = height;
    }

    public abstract double area();// 定义抽象方法，计算面积

}
```

 2）定义一个正方形类，该类继承自形状类 Shape，并重写了 area( ) 抽象方法。正方形类的代码如下： 

```java
public class Square extends Shape{

    public Square(int width, int height) {
        super(width, height);
    }
    // 重写父类中的抽象方法，实现计算正方形面积的功能
    @Override
    public double area() {
        return width*height;
    }
}
```

 3）定义一个三角形类，该类与正方形类一样，需要继承形状类 Shape，并重写父类中的抽象方法 area()。三角形类的代码实现如下： 

```java
public class Triangle extends Shape{
    public Triangle(int width, int height) {
        super(width, height);
    }

    @Override
    public double area() {
        return 0.5 * width * height;
    }
}
```

 4）最后创建一个测试类，分别创建正方形类和三角形类的对象，并调用各类中的 area() 方法，打印出不同形状的几何图形的面积。测试类的代码如下： 

```java
public class Test {
    public static void main(String[] args) {
        Square square=new Square(3,5);// 创建正方形类对象
        System.out.println("正方形的面积为："+square.area());
        Triangle triangle=new Triangle(3,4);// 创建三角形类对象
        System.out.println("三角形的面积为"+triangle.area());
    }
}

```

结果：

![1653709970218](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-68.png)

## 四、接口

### 4.1 定义

  接口相当于就是对外的一种约定和标准，这里拿操作系统据举栗子，为什么会有操作系统？就会为了屏蔽软件的复杂性和硬件的简单性之间的差异，为软件提供统一的标准。

在Java语言中，接口由`interface`关键字来表示，比如我们可以像下面这样定义一个接口

```java
public interface CxuanGoodJob{}
```

比如我们定义一个CxuanGoodJob的接口，然后就可以在其内部定义cxuan做的好那些事情，比如cxuan写的文章不错

```java
public interface CxuanGoodJob {
    void writeWell();
}
```

### 4.2 特征

 这里隐含了一些接口的特征：

- `interface`接口是一个完全抽象的类，他不会提供任何方法的实现，只是会进行方法的定义。
- 接口中只能使用两种访问修饰符，一种是`public`，他对整个项目可见；一种是`default`缺省值，他指具有包访问权限
- 接口只提供方法的定义，接口没有实现，但是接口可以被其他类实现。也就是说，实现接口的类需要提供方法的实现，实现接口使用`implements`关键字来表示，一个接口可以有多个实现。

```java
public class CxuanWriteWell implements CxuanGoodJob{
    @Override
    public void writeWell() {
        System.out.println("Cxuan write Job is vary well");
    }
}
```

- 接口不能实例化，所以接口中不能有任何构造方法，你定义构造方法会编译出错

## 五、Java抽象类和接口的区别

### 5.1 抽象类

在 Java 中，被关键字 abstract 修饰的类称为抽象类；被 abstract 修饰的方法称为抽象方法，抽象方法只有方法声明没有方法体。
抽象类有以下几个特点：

1. 抽象类不能被实例化，只能被继承。
2. 包含抽象方法的类一定是抽象类，但抽象类不一定包含抽象方法（抽象类可以包含普通方法）。
3. 抽象方法的权限修饰符只能为 public、protected 或 default，默认情况下为 public。
4. 一个类继承于一个抽象类，则子类必须实现抽象类的抽象方法，如果子类没有实现父类的抽象方法，那子类必须定义为抽象类。
5. 抽象类可以包含属性、方法、构造方法，但构造方法不能用来实例化对象，只能被子类调用。

### 5.2 接口

接口可以看成是一种特殊的类，只能用 interface 关键字修饰。
Java 中的接口具有以下几个特点：

1. 接口中可以包含变量和方法，变量被隐式指定为 public static final，方法被隐式指定为 public abstract（JDK 1.8 之前）。
2. 接口支持多继承，即一个接口可以继承（extends）多个接口，间接解决了 Java 中类不能多继承的问题。
3. 一个类可以同时实现多个接口，一个类实现某个接口则必须实现该接口中的抽象方法，否则该类必须被定义为抽象类。

### 5.3 抽象类和接口的区别

接口和抽象类很像，它们都具有如下特征。

- 接口和抽象类都不能被实例化，主要用于被其他类实现和继承。
- 接口和抽象类都可以包含抽象方法，实现接口或继承抽象类的普通子类都必须实现这些抽象方法。
  但接口和抽象类之间的差别非常大，这种差别主要体现在二者设计目的上。下面具体分析二者的差别。

从某种程度上来看，接口类似于整个系统的`总纲`，它制定了系统各模块应该遵循的标准，因此一个系统中的接口不应该经常改变。一旦接口被改变，对整个系统甚至其他系统的影响将是辐射式的，会导致系统中大部分类都需要改写。

除此之外，接口和抽象类在用法上也存在差别，如下表所示：

![1653713545063](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-69.png)

一个类最多只能有一个直接父类，包括抽象类，但一个类可以直接实现多个接口，通过实现多个接口可以弥补 Java 单继承的不足。

### 5.4 抽象类和接口的应用场景

抽象类的应用场景：

1. 父类只知道其子类应该包含怎样的方法，不能准确知道这些子类如何实现这些方法的情况下，使用抽象类。
2. 从多个具有相同特征的类中抽象出一个抽象类，以这个抽象类作为子类的模板，从而避免了子类设计的随意性。


接口的应用场景：

1. 一般情况下，实现类和它的抽象类之前具有 "is-a" 的关系，但是如果我们想达到同样的目的，但是又不存在这种关系时，使用接口。
2. 由于 Java 中单继承的特性，导致一个类只能继承一个类，但是可以实现一个或多个接口，此时可以使用接口。

 什么时候使用抽象类和接口： 

- 如果拥有一些方法并且想让它们有默认实现，则使用抽象类。
- 如果想实现多重继承，那么必须使用接口。因为 Java 不支持多继承，子类不能继承多个类，但可以实现多个接口，因此可以使用接口。
- 如果基本功能在不断改变，那么就需要使用抽象类。如果使用接口并不断需要改变基本功能，那么就需要改变所有实现了该接口的类。

## 六、多态 

### 6.1 概念

> 多态是指不同类的对象再调用同一个方法时呈现的多种不同行为。

![1653716908756](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-70.png)

通常来说，在一个类中定义的属性被其他类继承或重写，当把子类对象直接赋值给父类引用变量时，相同引用类型的变量调用同一个方法将呈现多种不同的形态。**通过多态，消除了类之间的耦合度，大大提高了程序的扩展性和可维护性。**

**Java的多态性是由类的继承、方法的重写以及父类引用指向子类对象实现的。**由于一个父类可以有多个子类，多个子类可以重写父类方法，并且多个不同的子类对象也可以指向同一个父类；这样，程序只有在运行时才知道具体代表的是哪个子类对象，这就体现了多态性。

### 6.2 案例

```java
public abstract class Animal { //定义抽象类
    public abstract void shout();//定义抽象方法
}
public class Dog extends Animal{//定义dog类继承Animal抽象类
    @Override
    public void shout() {//实现shout方法
        System.out.println("汪汪汪~~");
    }
}
public class Cat extends Animal {//定义cat类继承Animal抽象类
    @Override
    public void shout() {//实现shout方法
        System.out.println("喵喵喵~~~");
    }
}
public class Test {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.shout();
        Animal cat = new Cat();
        cat.shout();
    }
}
```

![1653716239632](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-71.png)

案例中定义了抽象类Animal和抽象方法shout，接着定义了两个类Cat和Dog继承Animal，在main方法中，分别创建Cat和Dog两个类对象同时指向同一个父类对象Aniaml，并调用shout（）方法，程序在编译时自动识别具体的子类对象，从而选择性的调用对应的方法，这就是Java中多态性的体现。

### 6.3 多态存在的三个必要条件

- 继承
- 重写
- 父类引用指向子类对象：`Parent p = new Child();`

![1653716994937](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-72.png)

```java
class Shape {
    void draw() {}
}
 
class Circle extends Shape {
    void draw() {
        System.out.println("Circle.draw()");
    }
}
 
class Square extends Shape {
    void draw() {
        System.out.println("Square.draw()");
    }
}
 
class Triangle extends Shape {
    void draw() {
        System.out.println("Triangle.draw()");
    }
}
```

### 6.4 多态的实现方式

#### 方式一：重写

#### 方式二：接口

- 生活中的接口最具代表性的就是插座，例如一个三接头的插头都能接在三孔插座中，因为这个是每个国家都有各自规定的接口规则，有可能到国外就不行，那是因为国外自己定义的接口类型。
-  java中的接口类似于生活中的接口，就是一些方法特征的集合，但没有方法的实现。具体可以看 [java接口](https://www.runoob.com/java/java-interfaces.html) 这一章节的内容。

#### 方式三：抽象类和抽象方法





# 内部类

## 1 概述

在 Java 中，允许在一个类的内部定义类，这样的类叫做内部类；这个内部类所在的类称为外部类。

一般来说，内部类分为`成员内部类、局部内部类、匿名内部类和静态内部类`。

## 2 成员内部类

 在一个类中除了可以定义成员变量、成员方法，还可以定义类，这样的类被称作成员内部类。在成员内部类中，可以访问外部类的所有成员，包括成员变量和成员方法；在外部类中，同样可以访问内部类的变量和方法。

#### 案例

```java
//定义Outer外部类
public class Outer {
        int m = 0;              //定义外部类变量
        void test1(){
            System.out.println("外部类方法");
        }
        //定义inner内部类
        class Inner{
            int n = 1;          //定义内部类变量
            //1.定义内部类方法，访问外部类成员变量和方法
            void show1(){
                System.out.println("外部类变量m=" + m);
                test1();
            }
            void show2(){
                System.out.println("内部类方法");
            }
        }
        //2.定义外部类方法，访问内部类变量和方法
        void test2(){
            Inner inner = new Inner();
            System.out.println("内部类成员变量n="+inner.n);
            inner.show2();
        }
}
//测试方法
public class Test {
    public static void main(String[] args) {
        Outer outer = new Outer();                  //创建外部类对象
        Outer.Inner inner =outer.new Inner();       //创建内部类对象
        inner.show1();                              //测试在成员内部类中访问外部类成员变量和方法
        outer.test2();                              //测试在外部类中访问内部类成员变量和方法
    }
}
```

**结果**

![1653809037480](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-73.png)

::: info 解析

案例中，定义了一个`外部类Outer`，在外部类中定义了成员变量、成员方法和`内部类Inner`。在内部类Inner中定义了内部类变量和两个**内部方法show1和show2**，show1中调用外部类的成员变量和成员方法，show2中输出内部方法。同时在Outer外部类中定义了test1方法输出外部类，test2方法调用内部类的成员变量和成员方法.

:::

::: tip 注意

内部类可以随心所欲的调用外部类的成员变量和成员方法，但是外部类要调用内部类的成员变量和成员方法，就 必须先创建一个成员内部类的对象，再通过这个对象来访问(第21行)。

:::

> 创建内部类的基本语法格式
>
> ```java
> 外部类名.内部类名 变量名 = new 外部类名( ).new 内部类名( );
> Outer.Inner    inner = new Outer( ).new Inner( );
> ```

## 3 局部内部类

局部内部类，也叫做方法内部类，就是定义在某个局部范围中的类，它和局部变量一样，都是在方法中定义的，其有效范围只限于方法内部。

在局部内部类中，局部内部类可以访问外部类所有的成员变量和方法，而局部内部类中的变量和方法**却只能在创建该局部内部类的方法中进行访问。**

**案例**

```java
//定义Outer外部类
public class Outer {
        int m = 10;                 //外部类成员变量
        void test1(){               //外部类方法
            System.out.println("外部类方法");
        }
        void test2() {
            class Inner {
                int n = 20;         //局部内部类变量

                void show() {       //局部内部类方法
                    System.out.println("外部类成员变量m=" + m);
                }
            }
            Inner inner = new Inner();
            System.out.println("局部类成员变量n=" + inner.n);
            inner.show();
        }
}
//测试方法
public class Test {
    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.test1();
        outer.test2();
    }
}
```

**结果**

![1653811145007](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-74.png)



## 3 静态内部类

所谓静态内部类，就是使用`static关键字`修饰的成员内部类。

与成员内部类相比，在形式上，静态内部类只是在内部类前增加了static关键字，但在功能上，静态内部类中只能访问外部类的静态成员，同时通过外部类访问静态内部类成员时，可以跳过外部类从而直接通过内部类访问静态内部类成员。

> 静态内部类的语法格式如下
>
> ```java
> 外部类名.静态内部类名 变量名 = new 外部类名.静态内部类名( );
> ```

案例

```java
//定义Outer外部类
public class Outer {
        static int m = 10;                 //外部类静态变量m
        static class Inner{
            void show(){
                //静态内部类访问外部类静态成员
                System.out.println("外部类静态变量m="+m);
            }
        }
}
//测试方法
public class Test {
    public static void main(String[] args) {
      Outer.Inner inner = new Outer.Inner();
      inner.show();
    }
}
```

![1653811656200](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-75.png)

::: tip 理解

 由于 static 关键字的存在，静态内部类是不允许访问外部类中非 static 的变量和方法的，这一点也非常好理解：**你一个静态的内部类访问我非静态的成员变量干嘛？** 

:::

## 4 匿名内部类

 **匿名类是指没有类名的内部类，必须在创建时使用 new 语句来声明类。** 

 匿名内部类是我们平常用得最多的，尤其是启动多线程的时候，会经常用到，并且 IDE 也会帮我们自动生成。 

语法格式如下

```java
new 类名或接口名(){
	重写方法;
}
```

匿名类有两种实现方式：

- 继承一个类，重写其方法。
- 实现一个接口（可以是多个），实现其方法。

```java
public interface Jumpping {
    void jump();
}
public class JumppdingOperator {
    public void method(Jumpping j){
        j.jump();
    }
}

public class JumppdingDemo {
    public static void main(String[] args) {
        JumppdingOperator jumppdingOperator = new JumppdingOperator();

        jumppdingOperator.method(new Jumpping() {
            @Override
            public void jump() {
                System.out.println("狗会飞了");
            }
        });
    }
}	
```

## 总结

为什么要使用内部类？

在《Think in java》中有这样一句话：

> 使用内部类最吸引人的原因是：每个内部类都能独立地继承一个（接口的）实现，所以无论外围类是否已经继承了某个（接口的）实现，对于内部类都没有影响。

在我们程序设计中有时候会存在一些使用接口很难解决的问题，这个时候我们可以利用内部类提供的、可以继承多个具体的或者抽象的类的能力来解决这些程序设计问题。可以这样说，接口只是解决了部分问题，而内部类使得多重继承的解决方案变得更加完整。

使用内部类还能够为我们带来如下特性（摘自《Think in java》）：

- 1、内部类可以使用多个实例，每个实例都有自己的状态信息，并且与其他外围对象的信息相互独立。
- 2、在单个外部类中，可以让多个内部类以不同的方式实现同一个接口，或者继承同一个类。
- 3、创建内部类对象的时刻并不依赖于外部类对象的创建。
- 4、内部类并没有令人迷惑的“is-a”关系，他就是一个独立的实体。
- 5、内部类提供了更好的封装，除了该外围类，其他类都不能访问。











# Java8的Lambda表达式 

## 为什么引入Lambda表达式

Lambda表达式是JDK8中一个重要的特性，它使用一个清晰简介的表达式来表达一个接口，同时Lambda表达式也简化了对集合以及数组数据的遍历、过滤和提取等操作。

## Lambda表达式入门

一个Lambda表达式由三个部分组成，分别为参数列表、“->”和表达式主体，其语法格式如下:

```java
([数据类型 参数名,数据类型 参数名,....])->{表达式主体}
```

**组成部分介绍：**

（1）([数据类型 参数名,数据类型 参数名,....])：用来向表达式传递接口方法需要的参数，**多个参数名中间必须用英文逗号分隔**。在编写Lambda表达式时，**可以省略参数的数据类型**，后面的表达式主体会自动进行校对和匹配。同时，如果只有一个参数，则可以省略括号( )。

（2）->：表示Lambda表达式箭牌，用来指定参数数据指向，**不能省略，且必须用英文横斜和大写号书写**

（3）{表达式主体}:**由单个表达式或语句块组成的主体，本质就是接口中对象方法的具体实现**，如果表达式主体只有一个语句，那么可以省略包含主体的大括号。另外，在Lambda表达式主体中允许有返回值，当只有一条return语句时，也可以省略return关键字。

**案例：**

```java
//定义动物类接口
interface Animal{
    void shout();       //定义方法shout()
}
public class Example01 {
    public static void main(String[] args) {
        String name = "小花";
        //1.匿名内部类作为参数传递给animalShout（）方法
        animalShout(new Animal(){
            public void shout(){
                System.out.println("匿名内部类输出："+name+"喵喵。。。。。");
            }
        });
        //2.使用Lambda表达式作为参数传递给animalShout()方法
        animalShout(()-> System.out.println("Lambda表达式输出："+name+"喵喵。。。。。"));
    }
    //创建一个animalShout()静态方法，接受接口类型的参数
    public static void animalShout(Animal an){
        an.shout();
    }
}
```

**案例中先定义了一个抽象方法的接口Animal,然后分别使用匿名内部类和Lambda表达式的方式实现了接口方法。**



















# 异常 

## 一、异常简介

 **Java 中的异常又称为例外，是一个在程序执行期间发生的事件，它中断正在执行程序的正常指令流。**为了能够及时有效地处理程序中的运行错误，必须使用异常类，这可以让程序具有极好的容错性且更加健壮。  

## 二、异常产生的原因及使用原则

在Java中一个异常的产生，主要有如下三种原因：

1. Java内部错误发生异常，Java虚拟机产生的异常。
2. 编写的程序代码中的错误所产生的异常，**例如空指针异常、数组越界异常等**。这种异常成为未检查的异常，一般需要在某些类中集中处理这些异常。
3. 通过**throw语句**手动生成的异常，这种异常称为检查的异常，一般用来告知该方法的调用者一些必要的信息。

Java通过面向对象的方法来处理异常。在一个方法的运行过程中，如果发生了异常，则这个方法会产生代表该异常的一个对象，并把它交给运行时的系统，运行时系统寻找相应的代码来处理这一异常。

**我们把生成异常对象，并把它交给运行时系统的过程称为**`抛出（throw）异常`。**运行时系统在方法的调用栈中查找，直到找到能够处理该类型异常的对象，这一过程称为**` 捕获（catch）异常 `.

 **Java 异常强制用户考虑程序的强健性和安全性。异常处理不应用来控制程序的正常流程，其主要作用是捕获程序在运行时发生的异常并进行相应处理。**编写代码处理某个方法可能出现的异常，可遵循如下三个原则： 

1. 在当前方法声明中使用try catch语句捕获异常。
2. 一个方法被覆盖时，覆盖它的方法必须抛出相同的异常或异常的子类。
3. 如果父类抛出多个异常，则覆盖方法必须抛出那些异常的一个子集，而不能抛出新的异常。

## 三、异常类型

在Java中所有异常类型都是内置类 java.lang.Throwable 类的子类，即Throwable位于异常类层次结构的顶层。 Throwable  类下有两个异常分支` Exception  `和` Error `。

![1654821671230](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-76.png)

由图可知Throwable类是所有异常和错误的超类，下面有Error和Exception两个子类分别表示错误和异常。其中异常类Exception又分为**运行时异常和非运行时异常**，这两种异常有很大的区别，也称为**不检查异常 （Unchecked Exception） 和检查异常 （Checked Exception）。**

- Exception类用于用户程序可能出现的异常情况，它也是用来创建自定义异常类型类的类。
- Error定义了在通常环境下不希望被程序捕获的异常。Error类型的异常用于Java运行时由系统显示与运行时环境系统本身有关的错误。堆栈溢出是这种错误的一例 。

**运行时异常**都是 RuntimeException 类及其子类异常，如 NullPointerException、IndexOutOfBoundsException 等，**这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理**。这些异常一般由程序逻辑错误引起，程序应该从逻辑角度尽可能避免这类异常的发生。 

- Java中常见运行时异常 

![1654822353775](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-77.png)

**非运行时异常**是指 RuntimeException 以外的异常，类型上都属于 Exception 类及其子类。从程序语法角度讲是必须进行处理的异常，如果不处理，程序就不能编译通过。如 IOException、ClassNotFoundException 等以及用户自定义的 Exception 异常（一般情况下不自定义检查异常）。 

-  Java常见非运行时异常 

![1654822517167](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-78.png)

## 四、try catch语句

Java的异常通过5个关键字来实现：try、catch、throw、throws和finally。**try catch语句用于捕获并处理异常，finally语句用于在任何情况下（除特殊情况下）都必须执行的代码，throw语句用于抛出异常，throws语句用于声明可能会出现的异常。**

try catch语句语法格式如下

```java
try{
	//可能发生异常的语句;
}catch(ExceptionType  e){
	//处理异常语句
}
```

在以上语法中，把可能引发异常的语句封装在try语句块中，用以捕获可能发生的异常。catch后的`（）`里放匹配的异常类，指明catch语句可以处理的异常类型，发生异常时产生异常类的实例化对象。

 如果 try 语句块中发生异常，那么一个相应的异常对象就会被拋出，然后 catch 语句就会依据所拋出异常对象的类型进行捕获，并处理。处理之后，程序会跳过 try 语句块中剩余的语句，转到 catch 语句块后面的第一条语句开始执行。

如果 try 语句块中没有异常发生，那么 try 块正常结束，后面的 catch 语句块被跳过，程序将从 catch 语句块后的第一条语句开始执行。

 ::: tip 注意

 try...catch 与 if...else 不一样 ,**try 后面的花括号`{}`不可以省略**，即使try块里只有一行代码，也不可以省略这个花括号。一直类似的是，**catch块后的花括号{}也不可以省略**。另外try块里声明的变量只是代码块内的局部变量，它只在try块内有效，其它地方不能访问该变量。

:::

在上面语法的处理代码块 1 中，可以使用以下 3 个方法输出相应的异常信息。

- printStackTrace() 方法：指出异常的类型、性质、栈层次及出现在程序中的位置。
- getMessage() 方法：输出错误的性质。
- toString() 方法：给出异常的类型与性质。

**案例**

编写一个录入学生姓名、年龄和性别的程序，要求能捕捉年龄不为数字时的异常。在这里使用 try catch 语句来实现，具体代码如下：

```java
public class ExceptionTest01 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("---------学生信息录入---------------");
        String name = "";   // 获取学生姓名
        int age = 0;        // 获取学生年龄
        String sex = "";    // 获取学生性别
        try {
            System.out.println("请输入学生姓名");
            name = scanner.next();
            System.out.println("获取学生年龄");
            age = scanner.nextInt();
            System.out.println("获取学生性别");
            sex = scanner.next();
        } catch (Exception e) {
            e.printStackTrace();
            System.out.println("输入有误！");
        }
        System.out.println("姓名：" + name);
        System.out.println("年龄：" + age);
        System.out.println("性别：" + sex);
    }
}
```

 上述代码在 main() 方法中使用 try catch 语句来捕获异常，将可能发生异常的`age = scanner.nextlnt();`代码放在了 try 块中，在 catch 语句中指定捕获的异常类型为 Exception，并调用异常对象的 printStackTrace() 方法输出异常信息。运行结果如下所示。 

![1654829123043](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-79.png)

## 五、try catch finally语句

在实际开发中，根据 try catch 语句的执行过程，try 语句块和 catch 语句块有可能不被完全执行，而有些处理代码则要求必须执行。例如，程序在 try 块里打开了一些物理资源（如数据库连接、网络连接和磁盘文件等），这些物理资源都必须显式回收。
所以为了确保一定能回收 try 块中打开的物理资源，异常处理机制提供了 finally 代码块，并且 Java 7 之后提供了）技术。

 finally 语句可以try catch 语句块匹配使用，语法格式如下： 

```java
try {
    // 可能会发生异常的语句
} catch(ExceptionType e) {
    // 处理异常语句
} finally {
    // 清理代码块
}
```

 对于以上格式，无论是否发生异常（除特殊情况外），finally 语句块中的代码都会被执行。此外，finally 语句也可以和 try 语句匹配使用，其语法格式如下： 

```java
try {
    // 逻辑代码块
} finally {
    // 清理代码块
}
```

::: tip  使用 try-catch-finally 语句时需注意以下几点 

1. 异常处理语法结构中只有 try 块是必需的，也就是说，如果没有 try 块，则不能有后面的 catch 块和 finally 块；
2. catch 块和 finally 块都是可选的，但 catch 块和 finally 块至少出现其中之一，也可以同时出现；
3. 可以有多个 catch 块，捕获父类异常的 catch 块必须位于捕获子类异常的后面；
4. 不能只有 try 块，既没有 catch 块，也没有 finally 块；
5. 多个 catch 块必须位于 try 块之后，finally 块必须位于所有的 catch 块之后。
6. finally 与 try 语句块匹配的语法格式，此种情况会导致异常丢失，所以不常见。

:::

 **一般情况下，无论是否有异常拋出，都会执行 finally 语句块中的语句**，执行流程如图 1 所示。

![未命名文件 (E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-80.png)](C:\Users\杨洲\Downloads\未命名文件 (1).png)

::: info try catch finally 语句块的执行情况可以细分为以下 3 种情况

1. 如果 try 代码块中没有拋出异常，则执行完 try 代码块之后直接执行 finally 代码块，然后执行 try catch finally 语句块之后的语句。
2. 如果 try 代码块中拋出异常，并被 catch 子句捕捉，那么在拋出异常的地方终止 try 代码块的执行，转而执行相匹配的 catch 代码块，之后执行 finally 代码块。如果 finally 代码块中没有拋出异常，则继续执行 try catch finally 语句块之后的语句；如果 finally 代码块中拋出异常，则把该异常传递给该方法的调用者。
3. 如果 try 代码块中拋出的异常没有被任何 catch 子句捕捉到，那么将直接执行 finally 代码块中的语句，并把该异常传递给该方法的调用者。

:::

除非在 try 块、catch 块中调用了退出虚拟机的方法`System.exit(int status)`，否则不管在 try 块或者 catch 块中执行怎样的代码，出现怎样的情况，异常处理的 finally 块总会执行。 

**案例**

 当 Windows 系统启动之后，即使不作任何操作，在关机时都会显示“谢谢使用”。下面编写 Java 程序使用 try catch finally 语句这个过程，具体代码如下： 

```java
public class ExceptionTest02 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Windows 系统已经启动");
        String[] pros = {"记事本","计算器","浏览器"};
        try {
            // 循环输出pros数组中的元素
            for (int i = 0;i<pros.length;i++){
                System.out.println(i+1+":"+pros[i]);
            }
            System.out.println("是否运行程序");
            String answer = input.next();
            if (answer.equals("y")){
                System.out.println("请输入程序编号");
                int number = input.nextInt();
                System.out.println("在运行程序["+pros[number-1]+"]");
            }else {
                System.out.println("输入错误，请重新输入");
            }
        } catch (Exception e) {
            e.printStackTrace();
        }finally {
            System.out.println("谢谢使用!");
        }
    }
}
```

 上述代码在 main() 方法中使用 try catch finally 语句模拟了系统的使用过程。当系统启动之后显示提示语，无论是否运行了程序，或者在运行程序时出现了意外，程序都将执行 finally 块中的语句，即显示“谢谢使用！”。输出时的结果如下所示。 

![1654829372484](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-81.png)

## 六、throws和throw：声明和抛出异常

Java中的异常处理除了捕获异常和处理异常之外，还包括声明异常和抛出异常。实现声明和抛出异常的关键字非常相似，它们是`throws和throw`。**可以通过throws关键字在方法上声明该方法要抛出的异常**，然后**在方法内部通过throw抛出异常对象**。

### 6.1、throws 声明异常

当一个方法产生一个它不处理的异常时，那么就需要在该方法的头部声明这个异常，以便将该异常传递到方法的外部进行处理。 使用 throws 声明的方法表示此方法不处理异常。throws 具体格式如下： 

```java
returnType method_name(paramList) throws Exception 1,Exception2,…{…}
```

其中，returnType表示返回值类型；method_name表示方法名；paramList表示参数列表；Exception1.Exception2，....表示异常类。

**如果有多个异常类，它们之间用逗号分隔。** 这些异常类可以是方法中调用了可能拋出异常的方法而产生的异常，也可以是方法体中生成并拋出的异常。 

使用throws声明抛出异常的思路是：当前方法不知道如何处理这种类型的异常，该异常应该由向上一级的调用者处理；如果main方法也不知道如何处理这种类型的异常，也可以使用throws声明抛出异常，该异常将交给JVM处理。JVM对异常的处理方法是：**打印异常的跟踪栈信息，并终止程序运行。**

### 6.2、throw 拋出异常

 与 throws 不同的是，**throw 语句用来直接拋出一个异常，**后接一个可拋出的异常类对象，其语法格式如下：

```javascript
throw ExceptionObject;
```

 其中，ExceptionObject 必须是 Throwable 类或其子类的对象。如果是自定义异常类，也必须是 Throwable 的直接或间接子类。例如，以下语句在编译时将会产生语法错误： 

```java
throw new String("拋出异常");    // String类不是Throwable类的子类
```


当 throw 语句执行时，它后面的语句将不执行，此时程序转向调用者程序，寻找与之相匹配的 catch 语句，执行相应的异常处理程序。如果没有找到相匹配的 catch 语句，则再转向上一层的调用程序。这样逐层向上，直到最外层的异常处理程序终止程序并打印出调用栈情况。

throw 关键字不会单独使用，它的使用完全符合异常的处理机制，但是，一般来讲用户都在避免异常的产生，所以不会手工抛出一个新的异常类的实例，而往往会抛出程序中已经产生的异常类的实例。 

**案例**

 在某仓库管理系统中，要求管理员的用户名需要由 8 位以上的字母或者数字组成，不能含有其他的字符。当长度在 8 位以下时拋出异常，并显示异常信息；当字符含有非字母或者数字时，同样拋出异常，显示异常信息。代码如下： 

```java
public class ExceptionTest03 {
    public boolean validateUserName(String username){
        boolean con = false;
        if (username.length() > 8){
            //判断用户长度是否大于8位
            for (int i = 0;i<username.length();i++){
                char ch = username.charAt(i);//获取每一个字符
                if ((ch > '0' && ch <= '9')|| (ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z')){
                    con = true;
                }else {
                    con = false;
                    throw new IllegalArgumentException("用户名只能由字母和数字组成！");
                }
            }
        }
        else{
            throw new IllegalArgumentException("用户名长度必须大于 8 位！");
        }
        return con;
    }

    public static void main(String[] args) {
        ExceptionTest03 e3 = new ExceptionTest03();
        Scanner input = new Scanner(System.in);
        System.out.println("请输入用户名");
        String username = input.next();
        try {
            boolean con = e3.validateUserName(username);
            if (con){
                System.out.println("用户名输入正确");
            }
        } catch (IllegalArgumentException e) {
            System.out.println(e);
        }
    }
}
```

 如上述代码，在 validateUserName() 方法中两处拋出了 IllegalArgumentException 异常，即当用户名字符含有非字母或者数字以及长度不够 8 位时。在 main() 方法中，调用了 validateUserName() 方法，并使用 catch 语句捕获该方法可能拋出的异常。

运行程序，当用户输入的用户名包含非字母或者数字的字符时，程序输出异常信息，如下所示。 

![1654832006641](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-82.png)

::: tip  throws 关键字和 throw 关键字在使用上的几点区别如下

- throws用来声明一个方法可能抛出的所有异常信息，表示出现一场的一种可能性，但并不一定会发生这些异常；throw则是指抛出一个具体的异常类型，执行throw则一定抛出了某种异常对象。
- 通过在一个方法（类）的声明处通过throws声明方法（类）可能抛出的异常信息，而在方法（类）内部通过throw声明一个具体的异常信息。
- throws通常不用显示地捕获信息，可由系统自动将所有捕获的异常信息抛给上级方法；throw则需要用户自己捕获相关的异常，而后在对其进行相关包装，最后将包装后的异常信息抛出。

:::

## 七、自定义异常

 如果Java提供的内置异常类型不能满足程序设计的需求，这时我们可以**自己设计 Java 类库或框架**，其中包括异常类型。**实现自定义异常类需要继承 Exception 类或其子类**，如果自定义运行时异常类需继承 RuntimeException 类或其子类。 

自定义异常的语法格式为：

```java
<class><自定义异常名><extends><Exception>
```

 在编码规范上，一般将自定义异常类的类名命名为 XXXException，其中 XXX 用来代表该异常的作用。

 **自定义异常类一般包含两个构造方法：一个是无参的默认构造方法，另一个构造方法以字符串的形式接收一个定制的异常消息，并将该消息传递给超类的构造方法。** 

 例如，以下代码创建一个名称为 IntegerRangeException 的自定义异常类： 

```java
class IntegerRangeException extends Exception{
	public IntegerRangeException(){
		super();
	}
	public IntegerRangeException(String s){
		super(s);
	}
}
```

以上代码创建的自定义异常类IntegerRangeException类继承自Exception类，在该类中包含两个构造方法。

案例

编写一个程序，对会员注册的年龄进行验证，即检测是否在0~100岁。

1）这里创建一个异常类MyException，并提供两个构造方法。MyException类的实现代码如下：

```java
    public class MyException extends Exception{
	public MyException(){
		super();
	}
	public MyException(String str){
		super(str)
	}
}
```

2）接着创建测试类，调用自定义异常类。代码实现如下：

```java
public class Test {
    public static void main(String[] args) {
        int age;
        Scanner input = new Scanner(System.in);
        System.out.println("请输入您的年龄");
        try {
            age = input.nextInt();      //获取年龄
            if (age<0){
                throw new MyException("您输入的年龄有误，请重新输入");
            } else if (age>100) {
                throw new MyException("您输入的年龄大于100，请重新输入");
            }else {
                throw new MyException("您的年龄为:"+age);
            }
        } catch (InputMismatchException e1) {
            System.out.println("输入的不是数字");
        }catch (MyException e2){
            System.out.println(e2.getMessage());
        }
    }
}
```

 3）运行该程序，当用户输入的年龄为负数时，则拋出 MyException 自定义异常，执行第二个 catch 语句块中的代码，打印出异常信息。程序的运行结果如下所示。 

![1654839469704](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-83.png)

当用户输入的年龄大于 100 时，也会拋出 MyException 自定义异常，同样会执行第二个 catch 语句块中的代码，打印出异常信息，如下所示。 

![1654839522589](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-84.png)

 在该程序的主方法中，使用了 if…else if…else 语句结构判断用户输入的年龄是否为负数和大于 100 的数，如果是，则拋出自定义异常 MyException，调用自定义异常类 MyException 中的含有一个 String 类型的构造方法。在 catch 语句块中捕获该异常，并调用 getMessage() 方法输出异常信息。

::: tip 提示

因为自定义异常继承自 Exception 类，因此自定义异常类中包含父类所有的属性和方法。 

:::









# 集合

## 概述

 在编程时，**可以使用数组来保存多个对象，但数组长度不可变化**，一旦在初始化数组时指定了数组长度，这个数组长度就是不可变的。如果需要保存数量变化的数据，数组就有点无能为力了。而且数组无法保存具有映射关系的数据，如成绩表为语文——79，数学——80，这种数据看上去像两个数组，但这两个数组的元素之间有一定的关联关系。

为了保存数量不确定的数据，以及保存具有映射关系的数据（也被称为关联数组），Java 提供了集合类。**集合类主要负责保存、盛装其他数据，因此集合类也被称为容器类。**Java 所有的集合类都位于 java.util 包下，提供了一个表示和操作对象集合的统一构架，包含大量集合接口，以及这些接口的实现类和操作它们的算法。

集合类和数组不一样，`数组元素既可以是基本类型的值，也可以是对象`（实际上保存的是对象的引用变量），而`集合里只能保存对象`（实际上只是保存对象的引用变量，但通常习惯上认为集合里保存的是对象）。

Java 集合类型分为 `Collection 和 Map`，它们是 Java 集合的根接口，这两个接口又包含了一些子接口或实现类。

## Collection

> 单列集合的根接口，用于存储一系列符合某种规则的元素。

Collection集合有两个重要的子接口，分别是List和Set。其中，List集合的特点是元素有序、可重复；Set集合的特点是元素无序且不可重复。**Lsit接口的主要实现类有ArryList和LinkedList；Set接口的主要实现类有HashSet和TreeSet**

![1654911734359](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-85.png)

## Map

> 双列集合的根接口，用于存储具有键（Key）、值（Value）映射关系的元素。

Map集合中的每个元素都包含一个键值，并且Key是唯一的，在使用Map集合时可以通过指定的Key找到对应的Vaule。例如根据一个学生的学号就可以找到对应的学生。**Map接口的主要实现类有HashMap和TreeMap**

![1654912106204](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-86.png)

# Collection接口

## 概述

**Collection接口是List、Set接口的父接口，通常情况下不被直接使用。**Collection接口定义了一些通用的方法，通过这些方法可以实现对集合的基本操作。定义的方法既可用于操作List集合，也可用于Set集合。

##  Collection接口的常用方法

|             方法名称              |                             说明                             |
| :-------------------------------: | :----------------------------------------------------------: |
|         boolean add(E e)          | 向集合中添加一个元素，如果集合对象被添加操作改变了，则返回 true。E 是元素的数据类型 |
|   boolean addAll(Collection c)    | 向集合中添加集合 c 中的所有元素，如果集合对象被添加操作改变了，则返回 true。 |
|           void clear()            |           清除集合中的所有元素，将集合长度变为 0。           |
|    boolean contains(Object o)     |                  判断集合中是否存在指定元素                  |
| boolean containsAll(Collection c) |            判断集合中是否包含集合 c 中的所有元素             |
|         boolean isEmpty()         |                       判断集合是否为空                       |
|       Iterator<E>iterator()       |         返回一个 Iterator 对象，用于遍历集合中的元素         |
|     boolean remove(Object o)      | 从集合中删除一个指定元素，当集合中包含了一个或多个元素 o 时，该方法只删除第一个符合条件的元素，该方法将返回 true。 |
|  boolean removeAll(Collection c)  | 从集合中删除所有在集合 c 中出现的元素（相当于把调用该方法的集合减去集合 c）。如果该操作改变了调用该方法的集合，则该方法返回 true。 |
|  boolean retainAll(Collection c)  | 从集合中删除集合 c 里不包含的元素（相当于把调用该方法的集合变成该集合和集合 c 的交集），如果该操作改变了调用该方法的集合，则该方法返回 true。 |
|            int size()             |                     返回集合中元素的个数                     |
|        Object[] toArray()         |   把集合转换为一个数组，所有的集合元素变成对应的数组元素。   |

**集合类就像容器，现实生活中容器的功能，就是添加对象、删除对象、清空容器和判断容器是否为空等，集合类为这些功能都提供了对应的方法。** 

## 案例

```java
public class CollectionMethod {
    public static void main(String[] args) {
        List list = new ArrayList();

        // add:添加单个元素
        list.add("java");
        list.add(20);
        list.add(true);
        System.out.println("add:添加单个元素->list="+list);
        // remove:删除指定元素
        list.remove(1);
        System.out.println("remove:删除指定元素->list="+list);
        // contains:查找元素是否存在
        boolean contains = list.contains(1);
        System.out.println("contains:查找元素是否存在->元素是否存在"+contains);
        // size:获取元素个数
        int size = list.size();
        System.out.println("size:获取元素个数->元素个数"+size);
        // isEmpty:判断是否为空
        boolean empty = list.isEmpty();
        System.out.println("isEmpty:判断是否为空->是否为空"+empty);
        // clear:清空
        list.clear();
        // addAll:添加多个元素
        List list2 = new ArrayList();
        list2.add("tom");
        list2.add(21);
        list2.add(true);
        list.addAll(list2);
        System.out.println("addAll:添加多个元素->list"+list);
        // containsAll:查找多个元素是否都存在
        System.out.println("containsAll:查找多个元素是否都存在->"+list.containsAll(list2));
        // removeAll：删除多个元素
        list.add("三国演义");
        list.removeAll(list2);
        System.out.println("removeAll：删除多个元素->"+list);
        // 说明：以 ArrayList 实现类来演示.
    }
}
```

**结果**

![1654997295743](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-87.png)

## Collection接口遍历

### Iterator遍历集合

**基本介绍**

1)Iteratorj对象称为迭代器，主要用于遍历Collection集合中的元素。
2)所有实现了Collection接口的集合类都有一个iterator0方法，用以返回
一个实现了Iterator接口的对象，即可以返回一个迭代器。
3)Iterator仅用于遍历集合，Iterator本身并不存放对象。

**案例**

```java
public class IteratorExample {
    public static void main(String[] args) {
        //创建ArrayList集合
        ArrayList list = new ArrayList();
        //向集合添加元素
        list.add("data_1");
        list.add("data_2");
        list.add("data_3");
        //获取Iterator对象
        Iterator iterator = list.iterator();
        //判断集合中是否存在下一个元素
        while (iterator.hasNext()) {
            Object obj =  iterator.next();
            System.out.println(obj);
        }
    }
}
```

**运行结果**

![1654997885939](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-88.png)

::: info 使用Iterator接口遍历集合时设计到的两个方法

1.  hasNext(); 

   1. 判断是否还有下一个元素
      1. 也就是调用hasNext()方法后就判断下一个位置上有没有元素,如果有的话就返回一个true,如果没有的话就返回一个false

2. next();

   ① 指针下移 

   ② 将指针下移之后位置上的元素返回 

3. 如果调用next()方法指针下移之后如果下移后位置上的集合元素为null时就会抛出一个NoSuchElementException(找不到元素)

:::

### foreach遍历集合

foreach循环用于遍历数组或集合中的元素，其具体语法格式如下：

```java
for(容器中元素类型 临时变量 : 容器变量){
	//执行语句
}
```

从格式可以看出，与for循环相比，foreach循环不需要获得容器的长度，也不需要根据索引访问容器中的元素，但它会自动遍历容器中的每个元素。

**案例**

```java
public class ForeachExample {
    public static void main(String[] args) {
        //创建ArrayList集合
        ArrayList list = new ArrayList();
        //向集合添加元素
        list.add("data_1");
        list.add("data_2");
        list.add("data_3");
        //使用foreach循环遍历
        for (Object obj: list) {
            System.out.println(obj);    //取出并打印集合中的元素
        }
    }
}
```

![1654997885939](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-88.png)

### JDK8的foreach遍历集合

在JDK8中，根据Lambda表达式特性还增加了一个forEach（Consumer action）方法来遍历集合，该方法所需要的参数是一个函数式接口。

**案例**

```java
public class ForeachExample {
    public static void main(String[] args) {
        //创建ArrayList集合
        ArrayList list = new ArrayList();
        //向集合添加元素
        list.add("data_1");
        list.add("data_2");
        list.add("data_3");
        System.out.println(list);
        //使用JDK8增加的forEach（Consumer action）循环遍历
        list.forEach(obj-> System.out.println("迭代集合元素"+obj));
    }
}
```

![1654999110561](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-88-1.png)

# List集合

## List概述

**List是一个有序、可重复的集合**，集合中的每个元素都有其对应的顺序索引。List集合允许使用重复元素，可以通过索引来访问指定位置的集合元素。List集合默认按元素的添加顺序设置元素的索引，第一个添加到List集合中的元素的索引为0，第二个为1，依此类推。

List**实现了Collection接口**，它主要有两个常用的实现类：**ArrayList类和LinkedList类**。

## List集合常用方法





## ArrayList类

 **ArrayList 类实现了可变数组的大小** ，存储在内的数据称为元素。它还**提供了快速基于索引访问元素的方式、对尾部成员的增加和删除支持较好**。使用ArrayList创建的集合，允许对集合中的元素进行快速的随机访问，不过，向ArrayList中插入与删除元素的速度相对较慢。

ArrayList类常用的构造方法有如下两种重载的形式：

- ArrayList():构造一个初始容量为10的空列表。
- ArrayList(Collection<?extends E>c>):构造一个包含指定Collection元素的列表，这些元素是按照该Collection的迭代器返回它们的顺序排序的。

 ArrayList 类除了包含 Collection 接口中的所有方法之外，还包括 List 接口中提供的如下表所示的方法。

|                   方法名称                    |                             说明                             |
| :-------------------------------------------: | :----------------------------------------------------------: |
|               E get(int index)                |   获取此集合中指定索引位置的元素，E 为集合中元素的数据类型   |
|              int index(Object o)              | 返回此集合中第一次出现指定元素的索引，如果此集合不包含该元 素，则返回 -1 |
|           int lastIndexOf(Object o)           | 返回此集合中最后一次出现指定元素的索引，如果此集合不包含该 元素，则返回 -1 |
|          E set(int index, Eelement)           | 将此集合中指定索引位置的元素修改为 element 参数指定的对象。 此方法返回此集合中指定索引位置的原元素 |
| List`<E>` subList(int fromlndex, int tolndex) | 返回一个新的集合，新集合中包含 fromlndex 和 tolndex 索引之间的所有元素。包含 fromlndex 处的元素，不包含 tolndex 索引处的元素 |

::: tip  注意 

 当调用 List 的 set(int index, Object element) 方法来改变 List 集合指定索引处的元素时，指定的索引必须是 List 集合的有效索引。例如集合长度为 4，就不能指定替换索引为 4 处的元素，也就是说这个方法不会改变 List 集合的长度。 

:::

**例1**

 使用 ArrayList 类向集合中添加三个商品信息，包括商品编号、名称和价格，然后遍历集合输出这些商品信息。 

1）创建一个商品类Product，在该类中定义3个属性和toString（）方法，分别实现 setter/getter 方法。代码的实现如下： 

```java
public class Product {
    // 商品类
    private int id; // 商品编号
    private String name; // 名称
    private float price; // 价格
    public Product(int id, String name, float price) {
        this.name = name;
        this.id = id;
        this.price = price;
    }
    // 这里是上面3个属性的setter/getter方法，这里省略
    public String toString() {
        return "商品编号：" + id + "，名称：" + name + "，价格：" + price;
    }
}
```

2）创建一个测试类，调用Product类的构造函数实例化三个对象，并将Product对象保存至ArrayList集合中。最后遍历该集合，输出商品信息。测试类的代码实现如下：

```java
public class Test {
    public static void main(String[] args) {
        Product pd1 = new Product(4, "木糖醇", 10);
        Product pd2 = new Product(5, "洗发水", 12);
        Product pd3 = new Product(3, "热水壶", 49);
        List list = new ArrayList();    //创建集合
        list.add(pd1);
        list.add(pd2);
        list.add(pd3);
        System.out.println("*************** 商品信息 ***************");
        for (int i = 0;i < list.size();i++){
            Product product =(Product) list.get(i);
            System.out.println(product);
        }
    }
}
```

该示例中的 ArrayList 集合中存放的是自定义类 Product 的对象，这与存储的 String 类的对象是相同的。与 Set 不同的是，List 集合中存在 get() 方法，该方法可以通过索引来获取所对应的值，获取的值为 Object 类，因此需要将该值转换为 Product 类，从而获取商品信息。

该程序的运行结果如下所示。 

![1654915339828](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-89.png)

## LinkedList类

 **LinkedList 类采用链表结构保存对象**， 这种结构的优点是**便于向集合中插入或者删除元素**。需要频繁向集合中插入和删除元素时，使用 LinkedList 类比 ArrayList 类效果高，但是 LinkedList 类随机访问元素的速度则相对较慢。这里的随机访问是指检索集合中特定索引位置的元素。 

 LinkedList 类除了包含 Collection 接口和 List 接口中的所有方法之外，还特别提供了下表所示的方法。 

|      方法名称      |             说明             |
| :----------------: | :--------------------------: |
| void addFirst(E e) | 将指定元素添加到此集合的开头 |
| void addLast(E e)  | 将指定元素添加到此集合的末尾 |
|    E getFirst()    |    返回此集合的第一个元素    |
|    E getLast()     |   返回此集合的最后一个元素   |
|  E removeFirst()   |   删除此集合中的第一个元素   |
|   E removeLast()   |  删除此集合中的最后一个元素  |

**案例**

## ArrayList 类和 LinkedList 类的区别

 ArrayList 与 LinkedList 都是 **List 接口的实现类**，因此都实现了 List 的所有未实现的方法，只是实现的方式有所不同 

 ArrayList 是基于**动态数组数据结构**的实现，访问元素速度优于 LinkedList。LinkedList 是基于链表数据结构的实现，占用的内存空间比较大，但在批量插入或删除数据时优于 ArrayList。

对于快速访问对象的需求，使用 ArrayList 实现执行效率上会比较好。需要频繁向集合中插入和删除元素时，使用 LinkedList 类比 ArrayList 类效果高。

不同的结构对应于不同的算法，有的考虑节省占用空间，有的考虑提高运行效率，对于程序员而言，它们就像是“熊掌”和“鱼肉”，不可兼得。高运行速度往往是以牺牲空间为代价的，而节省占用空间往往是以牺牲运行速度为代价的。 

# Set集合

## 概念

**Set系列集合特点：**

- 无序：存取顺序不一致
- 不重复：可以去除重复
- 无索引：没有带索引的方法，所以不能使用普通for循环遍历，也不能通过索引获取元素。

Set**实现了Collection接口**，它主要有两个常用的实现类：**HashSet类和TreeSet类**

![1654993837755](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-91.png)

**Set集合实现类特点：**

- HashSet:无序、不重复、无索引
- LinkedHashset:有序、不重复、无索引
- TreeSet:排序、不重复、无索引

## HashSet类

**HashSet是Set接口的典型实现**，大多数时候使用Set集合时就是使用这个实现类。HashSet是按照Hash算法来存储集合中的元素。因此**具有很好的存取和查找性能**。

HashSet具有以下特点：

- 不能保证元素的排序顺序，顺序可能与添加顺序不同，顺序也有可能发生变化。
- HashSet不能同步，如果多个线程同时访问或修改一个HashSet，则必须通过代码来保证其同步。
- 集合元素值可以是null

当向 HashSet 集合存放一个元素时， HashSet  会调用该对象的`hashCode()`方法来得到该对象的 **hashCode值**，然后根据hashCode值觉得该对象在HashSet 中的存储位置。如果有两个元素通过equals()方法比较返回的结果为true，但它们的hashCode不相等，HashSet将会把它们存储在不同的位置，依然可以添加成功。

 **也就是说，两个对象的 hashCode 值相等且通过 equals() 方法比较返回结果为 true，则 HashSet 集合认为两个元素相等。** 

在HashSet类中实现了Collection接口中的所有方法。HashSet类的常用构造方法重载形式如下。

- HashSet()：构造了一个新的空的Set集合。
- HashSet(Collection<?extends E>c):构造一个包含指定的Collection集合元素的新的Set集合。其中，"< >"中的extends表示HashSet的父类，即指明该Set集合中存放的集合元素类型。c表示其中的元素被存放在此Set集合中。

 下面的代码演示了创建两种不同形式的 HashSet 对象。 

```java
HashSet hs = new HashSet();    // 调用无参的构造函数创建HashSet对象
HashSet<String> hss = new HashSet<String>();    // 创建泛型的 HashSet 集合对象anl 
```

**案例**

编写一个Java程序，使用HashSet创建一个Set集合，并向该集合中添加 4 套教程。具体实现代码如下： 

```java
public class Example01 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        String course1 = "微积分A";
        String course2 = "微积分B";
        String course3 = "线性代数";
        String course4 = "概率论";
        set.add(course1);// 将 course1 存储到 Set 集合中
        set.add(course2);// 将 course2 存储到 Set 集合中
        set.add(course3);// 将 course3 存储到 Set 集合中
        set.add(course4);// 将 course4 存储到 Set 集合中
        System.out.println("数学教程有：");
        Iterator iterator = set.iterator();
        while (iterator.hasNext()) {
            Object next = iterator.next();
            System.out.println(next);
        }
        System.out.println("有" + set.size() + "套精彩教程！");
    }
}
```

运行结果如下：

![1655001710294](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-92.png)

::: tip 注意

 在以上示例中，如果再向 CourseSet 集合中再添加一个名称为“微积分A”的 String 对象，则输出的结果与上述执行结果相同。也就是说，**如果向 Set 集合中添加两个相同的元素，则后添加的会覆盖前面添加的元素，即在 Set 集合中不会出现相同的元素**。 

:::

## TreeSet

**TreeSet类同时实现了Set接口和SortedSet接口。SortedSet接口是Set接口的子接口，可以实现对集合进行自然排序**，因此使用TreeSet类实现的Set接口默认情况下是自然排序的，这里的自然排序指的是升序排序。

TreeSet只能对是实现了Comparable接口的类对象进行排序，因为Comparable接口中有一个compareTo（Object o）方法用于比较两个对象的大小。例如a.compareTo(b),如果a=b，则该方法返回0；如果a>b， 则该方法返回大于 0 的值；如果 a < b，则该方法返回小于 0 的值。 

 👇表列举了 JDK 类库中实现 Comparable 接口的类，以及这些类对象的比较方式。 

|                              类                              |                  比方式                   |
| :----------------------------------------------------------: | :---------------------------------------: |
| 包装类（BigDecimal、Biglnteger、 Byte、Double、Float、Integer、Long 及 Short) |              按数字大小比较               |
|                          Character                           |     按字符的 Unicode 值的数字大小比较     |
|                            String                            | 按字符串中字符的 Unicode 值的数字大小比较 |

 TreeSet 类除了实现 Collection 接口的所有方法之外，还提供了如👇表所示的方法。

![1655002143056](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-93.png)

::: tip  注意

表面上看起来这些方法很多，其实很简单。因为 TreeSet 中的元素是有序的，所以增加了访问第一个、前一个、后一个、最后一个元素的方法，并提供了 3 个从 TreeSet 中截取子 TreeSet 的方法。 

:::

**案例**

 本次有 5 名学生参加考试，当老师录入每名学生的成绩后，程序将按照从低到高的排列顺序显示学生成绩。此外，老师可以查询本次考试是否有满分的学生存在，不及格的成绩有哪些，90 分以上成绩的学生有几名。 

 下面使用 TreeSet 类来创建 Set 集合，完成学生成绩查询功能。具体的代码如下： 

```java
public class Example02 {
    public static void main(String[] args) {
        TreeSet<Double> scores = new TreeSet<>();   // 创建 TreeSet 集合
        Scanner input = new Scanner(System.in);
        System.out.println("------------学生成绩管理系统-------------");
        for (int i = 0;i < 5 ; i++){
            System.out.println("第"+(i+1)+"学生的成绩");
            double score = input.nextDouble();      //输入学生成绩
            scores.add(score);                      //将学生成绩存储到TreeSet集合中
        }
        Iterator<Double> it = scores.iterator(); // 创建 Iterator 对象
        System.out.println("学生成绩从低到高的排序为：");
        while (it.hasNext()) {
            System.out.print(it.next() + "\t");
        }
        System.out.println("\n请输入要查询的成绩");
        double searchScore = input.nextDouble();
        if (scores.contains(searchScore)){
            System.out.println("成绩为： " + searchScore + " 的学生存在！");
        }else {
            System.out.println("成绩为： " + searchScore + " 的学生不存在！");
        }
        // 查询不及格的学生成绩
        SortedSet<Double> score1 = scores.headSet(60.0);
        System.out.println("\n不及格的成绩有：");
        for (int i = 0;i < score1.toArray().length;i++){
            System.out.print(score1.toArray()[i] + "\t");
        }
        // 查询90分以上的学生成绩
        SortedSet<Double> score2 = scores.tailSet(90.0);
        System.out.println("\n90 分以上的成绩有：");
        for (int i = 0;i < score2.toArray().length;i++){
            System.out.print(score2.toArray()[i] + "\t");
        }
    }
}
```

运行结果：

![1655003743965](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-94.png)

::: 注意

在使用自然排序时只能向 TreeSet 集合中添加相同数据类型的对象，否则会抛出 ClassCastException 异常。如果向 TreeSet 集合中添加了一个 Double 类型的对象，则后面只能添加 Double 对象，不能再添加其他类型的对象，例如 String 对象等。 

:::

# Map集合

## 概念

**Map是一种键-值对 （key-value）集合** ，Map集合中的每个元素都包含一个键（key）对象和一个值（value）对象。**用于保存具有映射关系的数据**。

Map集合里保存着两组值，一组值用于保存Map里的key，另外一组值用于保存Map里的value，**key和value都可以是任何引用类型的数据**。Map的key不允许重复，value可以重复，**即同一个Map对象的任何两个key通过equals方法比较总是返回false**。

Map中的key和value之间存在单向一对一关系，即通过指定的key，总能找到唯一的、确定的value。从Map中取出的数据时，只要给出指定的key，就可以取出对应的value。

**Map接口主要有两个实现类：HashMap类和TreeMap类，其中， HashMap 类按哈希算法来存取键对象，而 TreeMap 类可以对键对象进行排序**。

## 常用方法

  Map 接口中提供的常用方法如表 1 所示。 

![1655004222545](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-95.png)

 Map 集合最典型的用法就是成对地添加、删除 key-value 对，接下来即可判断该 Map 中是否包含指定 key，也可以通过 Map 提供的 keySet() 方法获取所有 key 组成的集合，进而遍历 Map 中所有的 key-value 对。下面程序示范了 Map 的基本功能。 

## HashMap

### HashMap实例

 每名学生都有属于自己的唯一编号，即学号。在毕业时需要将该学生的信息从系统中移除。

下面编写 Java 程序，使用 HashMap 来存储学生信息，其键为学生学号，值为姓名。毕业时，需要用户输入学生的学号，并根据学号进行删除操作。具体的实现代码如下： 

```java
public class MapExample01 {
    public static void main(String[] args) {
        HashMap students = new HashMap();
        students.put("11","赵三");
        students.put("22","李四");
        students.put("33","王五");
        students.put("44","张三");
        System.out.println("******** 学生列表 ********");
        Iterator iterator = students.keySet().iterator();
        while (iterator.hasNext()) {
            Object key =  iterator.next();
            Object val = students.get(key);
            System.out.println("学号:"+key+"，姓名："+val);
        }
        Scanner input = new Scanner(System.in);
        System.out.println("请输入要删除的学号");
        int num = input.nextInt();
        if (students.containsKey(String.valueOf(num))){ // 判断是否包含指定键
            students.remove(String.valueOf(num)); // 如果包含就删除
        }else{
            System.out.println("该学生不存在！");
        }
        System.out.println("******** 学生列表 ********");
        iterator =  students.keySet().iterator();
        while (iterator.hasNext()) {
            Object key =  iterator.next();
            Object val = students.get(key);
            System.out.println("学号:"+key+"，姓名："+val);
        }
    }
}
```

在该程序中，两次使用 while 循环遍历 HashMap 集合。当有学生毕业时，用户需要输入该学生的学号，根据学号使用 HashMap 类的 remove() 方法将对应的元素删除。程序运行结果如下所示。 

运行结果如下：

![1655004774089](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-96.png)

::: tip  注意

TreeMap 类的使用方法与 HashMap 类相同，唯一不同的是 TreeMap 类可以对键对象进行排序，这里不再赘述。 

:::









## TreeMap

TreeMap是`SortedMap接口`的实现类，TreeMap底层是`红黑树`数据结构，每个`key-value`作为红黑树的一个`节点`。TreeMap存储节点时，`根据key对节点进行排序`，主要是自然排序和自定义排序。在TreeMap内部是通过二叉树的原理来保证键的唯一性，类似于TreeSet。

**案例：**

```java
public class Example01 {
    public static void main(String[] args) {
        Map map = new TreeMap();
        map.put("1","Jack");
        map.put("2","Rose");
        map.put("3","Mary");
        map.put("4","Lucy");
        System.out.println(map);
    }
}
```

运行结果如下：

![1655168090212](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-97.png)



上述案例中，首先创建了一个TreeMap集合，并使用put()方法按顺序向集合中添加了3个元素，然后打印出集合信息。从运行结果可以看出，取出的元素按照键对象的自然排序进行了排序，这是因为添加的元素中键对象是String类型，String类型实现了**Comparable接口**，因此默认会按照自然排序对元素进行排序。

同TreeSet集合一样，在使用TreeMap集合时，也可以通过自定义`比较器Comparator`的方式对所有的键进行定制排序。接下来对上述案例进行修改，将集合中的元素**按照键对象由大到小排序**

```java
//自定义比较器
class CustomComparator implements Comparator{
    public int compare(Object obj1,Object obj2){
        String key1 = (String) obj1;
        String key2 = (String) obj2;
        return key2.compareTo(key1); //将比较之后的值返回
    }
}
public class Example02 {
    public static void main(String[] args) {
        Map map = new TreeMap(new CustomComparator());
        map.put("2","Rose");
        map.put("4","Lucy");
        map.put("1","Jack");
        map.put("3","Mary");
        System.out.println(map);
    }
}
```

运行结果如下：

![1655169210236](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-98.png)

修改案例中，定义了比较器CustomComparator针对String类型的键对象key进行比较，在实现compare()方法时，调用了String对象的compareTo()方法。由于方法中返回的是“key2.compareTo(key1)”因此最终输出结果中的元素按照键对象从大到小的顺序进行了排序。

## Properties集合

Map接口还有一个实现类Hashtable，它和HashMap十分相似，其中一个主要区别在于Hashtable线程是安全的。另外在使用方面，Hashtable的效率也不及HashMap，所以，目前基本上被HashMap取代，但是Hashtable类有一个字类Properties在实际应用中非常重要。Properties主要用来存储字符串类型的键和值，在实际开发中，经常使用Properties集合来存取应用的配置项。

假设有一个文本编辑工具，要求默认背景色是红色，字体大小是14px。语言为中文，这些要求就可以使用Properties集合类对应的properties文件进行配置，效果如下图所示

![1655170329512](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-99.png)



```java
public class Example01 {
    public static void main(String[] args) throws IOException {
        //1.通过Properties进行属性文件读取操作
        Properties properties = new Properties();
        //加载要读取的文件test.properties
        properties.load(new FileInputStream("E:\\IdeaProjects\\Java学习\\collection-Map\\src\\Properties\\test.properties"));
        //遍历test.properties键值对元素信息
        properties.forEach((k,v)-> System.out.println(k+"-"+v));
        //2.通过Properties进行属性文件写入操作
        //指定要写入操作的文件名称和位置
        FileOutputStream out = new FileOutputStream("E:\\IdeaProjects\\Java学习\\collection-Map\\src\\Properties\\test.properties");
        //向Properties类文件进行写入键值对信息
        properties.setProperty("charset","UTF-8");
        //将此Properties集合中新增的键值对信息写入配置文件
        properties.store(out,"新增charset编码");
    }
}
```

```properties
# test.properties
Background-color=red
Font-size=14px
language=chinese
```

运行结果如下：

![1655170374086](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-100.png)

::: info 解析

案例中，首先创建了Properties集合对象，然后通过I/O流的形式读取了test.properties配置文件中的内容，并进行遍历，完成了Properties集合读取properties配置文件的操作。接着，同样通过1/0流的形式指定了要进行写人操作的文件地址和名称，使用Properties的setProperty()方法新增了一个健值对元素，并使用store()方法将新增信息写人到opres配置文件中。在该文件中涉及的配置文件test.properties是通过I/O流的形式进行操作的

:::

## Map集合遍历

### Interator迭代器遍历map集合

使用Interator迭代器遍历map集合，需要先将Map集合转换为Iterator接口对象，然后进行遍历，由于Map集合中元素是由键值对组成，所以使用Interator接口遍历Map时，会有两种将Map集合转换为Interator接口对象再遍历的方法，即keySet()方法和entrySet()方法。

其中，**keySet()方法，需要将Map集合中所有的键对象转换为Set单列集合，接着将包含键对象的Set集合转换为Interator接口对象，然后遍历Map集合中的所有的键，再根据键获取相应的值**。

#### keySet()方法

```java
public class keySet {
    public static void main(String[] args) {
        Map map = new HashMap();    //创建map集合
        map.put("1","jack");        //存储元素
        map.put("2","mary");        //存储元素
        map.put("3","Lucy");        //存储元素
        System.out.println(map);
        Set keySet = map.keySet();  //获取键的集合
        Iterator it = keySet.iterator();
        while (it.hasNext()) {
            Object key = it.next();
            Object value = map.get(key);    //获取每个键对应的值
            System.out.println(key+":"+value);
        }
    }
}
```

运行结果如下图：

![1655172532739](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-101.png)

::: info 解析

上述案例中，首先调用Map对象的KeySet()方法，获得存储Map集合中所有键的Set集合，然后通过Iterator迭代Set集合的每一个键元素，最后通过get(Objectkey)方法，根据键获取对应的值。

:::

Map集合中的另外一中通过Iterator迭代器遍历集合的方式是使用entrySet()方法，该方法将原有Map集合中的键值对作为一个整体返回为Set集合，接着将包含键值对对象的Set集合转换为Iterator接口对象，然后获取集合中所有键值对映射关系，再从映射关系中取得键和值。

#### entrySet()方法

```java
public class entrySet {
    public static void main(String[] args) {
        Map map = new HashMap();    //创建map集合
        map.put("1","jack");        //存储元素
        map.put("2","mary");        //存储元素
        map.put("3","Lucy");        //存储元素
        System.out.println(map);
        Set entrySet = map.entrySet();
        Iterator iterator = entrySet.iterator();
        while (iterator.hasNext()) {
            Map.Entry entry = (Map.Entry)(iterator.next());
            Object key =  entry.getKey();
            Object value = entry.getValue();
            System.out.println(key+":"+value);
        }
    }
}	
```

::: info 解析

在上述案例中，首先调用Map对象的entrySet()方法获得存储Map中的所有键值对映射的Set集合，这个集合中存放了Map.Entry类型的元素(Entry是Map接口内部类)，每个Map.Entry对象代表Map中的一个键值对，然后迭代Set集合，获得每一个映射对象，并调用映射对象的getKey()和getValue()方法获取键和值。

### forEach()方法遍历Map集合

与Collection集合遍历类上，在JDK8中也根据Lambda'表达式特性新增了一个forEach(BiConsumer action)方法来遍历Map集合，该方法需要的参数也是一个函数式接口，因此可以使用Lambda表达式的书写形式来进行集合遍历

**案例：**

```java
public class forEach {
    public static void main(String[] args) {
        Map map = new HashMap();    //创建map集合
        map.put("1","jack");        //存储元素
        map.put("2","mary");        //存储元素
        map.put("3","Lucy");        //存储元素
        System.out.println(map);
        map.forEach((key,value)-> System.out.println(key+":"+value));
    }
}	
```

**运行结果如下**：

![1655172532739](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-101.png)

::: info 解析

上述案例中，使用forEach(BiConsumer action)方法对集合中的元素进行遍历，该方法传递的是一个Lambda表达式书写的函数式接口BiConsumer。forEach(BiConsumer action)方法在执行时，会自动遍历集合元素的键和值并将结果逐个传递给Lambda表达式的形参。

在Map集合中除上述两种主要的遍历方式外，还提供了一个values()方法，通过这个方法可以直接获取Map中存储所有值的Collection集合。

**案例：**

```java
public class Example {
    public static void main(String[] args) {
        Map map = new HashMap();    //创建map集合
        map.put("1","jack");        //存储元素
        map.put("2","mary");        //存储元素
        map.put("3","Lucy");        //存储元素
        System.out.println(map);
        Collection values = map.values();//获取Map集合中value值集合对象
        //遍历Map集合所有值对象value
        values.forEach(value-> System.out.println(value));
    }
}
```

运行结果如下：

![1655174241763](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-102.png)



















​    

# 泛型

## 概述

泛型在 java 中有很重要的地位，在面向对象编程及各种设计模式中有非常广泛的应用。

:partly_sunny: 什么是泛型？为什么要使用泛型？

泛型，即“**参数化类型**”。一提到参数，最熟悉的就是定义方法时有形参，然后调用此方法时传递实参。那么参数化类型怎么理解呢？

顾名思义，就是**将类型由原来的具体的类型参数化，类似于方法中的变量参数，此时类型也定义成参数形式（可以称之为类型形参）**，然后在使用/调用时传入具体的类型（类型实参）。

泛型的本质是为了参数化类型（在不创建新的类型的情况下，通过泛型指定的不同类型来控制形参具体限制的类型）。也就是说在泛型使用过程中，

操作的数据类型被指定为一个参数，这种参数类型可以用在类、接口和方法中，分别被称为泛型类、泛型接口、泛型方法。

**泛型作用：**可以在类声明时通过一个标识表示类中某个属性的类型或者是某个方法的返回值类型或者是参数类型

## 泛型方法

你可以写一个泛型方法，该方法在调用时可以接受不同类型的参数。根据传递给泛型方法的参数类型，编译器适当地处理每一个方法调用。

::: tip 定义泛型方法的规则

- 所有泛型方法声明都有一个类型参数声明部分（**由尖括号分隔**），该类型参数声明部分在方法返回类型之前（在下面例子中`<E>`）。
- 每一个类型参数声明部分**包含一个或多个类型参数，参数间用逗号隔开**。一个泛型参数，也被称为一个类型变量，是用于指定一个泛型类型名称的标识符。
- 类型参数能被用来声明返回值类型，并且能作为泛型方法得到的实际参数类型的占位符。
- 泛型方法的方法体的声明和其他方法一样。注意类型参数只能代表引用型类型，不能是原始类型（像int，double，char等）

:::

**实例**

下面的例子演示了如何使用泛型方法打印不同字符串的元素：

```java
public class GenericMethodTest {
    //泛型方法printArray
    public static<E> void printArray(E[] inputArray){
        //输出数组元素
        for (E element:inputArray){
            System.out.printf("%s",element);
        }
        System.out.println();
    }

    public static void main(String[] args) {
        //创建不同类型的数组：Integer,Double和Character
        Integer[] intArray = {1,2,3,4,5};
        Double[] doubleArray = {1.1,2.2,3.3,4.4};
        Character[] charArray = {'A','B','C','D'};
        System.out.println("Array integerArray contains");
        printArray(intArray);// 传递一个整型数组
        System.out.println("\nArray doubleArray contains");
        printArray(doubleArray); // 传递一个双精度型数组
        System.out.println("\nArray charArray contains");
        printArray(charArray); // 传递一个字符型型数组
    }
}
```

 **运行结果如下所示：** 

![1655261575733](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-103.png)



## 泛型类

泛型类的声明和非泛型的声明类似，除了在类名后面添加了类型参数声明部分。

和泛型方法一样，**泛型类的类型参数声明部门也包含一个或多个类型参数，参数之间用逗号隔开**。一个泛型参数，也被称为一个类型变量，是用于指定一个泛型类型名称的标识符。因为他们接受一个或多个参数，这些类型被称为参数化的类或参数化的类型。

**实例**

如下实例演示了我们如何定一个泛型类：

```java
public class Box<T> {
    private T t;
    public void add(T t){
        this.t = t;
    }
    public T get(){
        return t;
    }

    public static void main(String[] args) {
        Box<Integer> integerBox = new Box<Integer>();
        Box<String> stringBox = new Box<String>();

        integerBox.add(10);
        stringBox.add("Hello World！");

        System.out.printf("Integer Value :%d\n\n",integerBox.get());
        System.out.printf("String Value :%s\n\n",stringBox.get());
    }
}
```

 **运行结果如下所示：** 

![1655262205274](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-104.png)



























# 常用工具类

## Collections工具类

在Java中，针对集合的操作非常频繁，例如将集合中的元素排序、从集合中查找元素等，针对这些常见操作，Java提供了一个工具类专门用来操作集合，这个类就是`Collections`，它位于java.util包中。Collections提供了大量的静态的方法用于对集合中元素进行排序、查找和修改等操作。

### 添加、排序操作

Collections类中提供了一系列方法用于对List集合进行添加和排序的操作，例如下表

|                           方法声明                           |                   功能描述                   |
| :----------------------------------------------------------: | :------------------------------------------: |
| static`<T>`boolean addAll(Collection<? super T>c,T···elements) |       将所有指定元素添加到指定集合c中        |
|                static void reverse(List list)                |         反转指定List集合中元素的顺序         |
|                static void shuffle(List list)                |        对List集合中的元素进行随机排序        |
|                 static void sort(List list)                  | 根据元素的自然排序对List集合中的元素进行排序 |
|           static void swap(List list,int i,int j)            | 将指定List集合中角标i处元素和j处元素进行交换 |

**实例**

```java
public class Example01 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        Collections.addAll(list,"C","Z","B","K");   //添加元素
        System.out.println("排序前"+list);
        Collections.reverse(list);                              //反转元素
        System.out.println("反转后"+list);
        Collections.sort(list);                                 //按照自然排序
        System.out.println("按照自然排序后"+list);
        Collections.shuffle(list);
        System.out.println("按照随机排序后"+list);                 //按照随机排序
        Collections.swap(list,0,list.size()-1);
        System.out.println("集合首尾元素交换后"+list);             //集合首尾元素交换
    }
}
```

**运行结果如下：**

![1655264074457](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-105.png)

### 查找、替换操作

Collections还提供了一些常用方法用于对查找和替换集合中的元素，如下表

|                           方法声明                           |                           功能描述                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|        static int binarySearch(List list,Obejct key)         | 使用二分法搜索指定对象在List集合中的索引，查找的List集合中的元素必须是有序的 |
|              static Object max(Collection col)               |         根据元素的自然顺序，返回给定集合中最大的元素         |
|              static Object min(Collection col)               |         根据元素的自然顺序，返回给定集合中最小的元素         |
| static boolean replaceAll(List list,Obejct oldVal,Obejct newVal) |          用一个新值newVal替换掉List集合中旧值oldVal          |

**实例**

```java
public class Example02 {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();
        Collections.addAll(list,-3,2,6,1,8);       //向集合中添加所有指定元素
        System.out.println("集合中的元素"+list);
        System.out.println("集合中的最大元素"+Collections.max(list));
        System.out.println("集合中的最小元素"+Collections.min(list));
        Collections.replaceAll(list,8,1);      //将集合中的8用1替换
        System.out.println("替换过后的集合"+list);
        Collections.sort(list);                                 //使用二分法查找前，必须保证元素有序
        System.out.println("排序后的集合"+list);
        int index = Collections.binarySearch(list,2);
        System.out.println("使用二分法查找元素2所在位置"+index);
    }
}
```

**运行结果如下：**

![1655264772094](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-106.png)

## Arrays工具类

  Arrays类是一个工具类，其中包含了数组操作的很多方法，这个Arrays类里均位static修饰的方法（static修饰的方法可以直接通过类名调用），可以直接通过Arrays.xxx(xxx)的形式调用方法。

**1)int binarySearch(type[]a,type key)**

 使用二分法查询 key 元素值在 a 数组中出现的索引，如果 a 数组不包含 key 元素值，则返回负数。调用该方法时要求数组中元素己经按升序排列，这样才能得到正确结果。 

**2)int binarySearch(type[]a,int fromindex,int toindex,type key)**

 这个方法与前一个方法类似，但它只搜索 a 数组中 fromIndex 到 toIndex 索引的元素。调用该方法时要求数组中元素己经按升序排列，这样才能得到正确结果。 

**3）type[] copyOf(type[] original, int length)**

这个方法将会把 original 数组复制成一个新数组，其中 length 是新数组的长度。如果 length 小于 original 数组的长度，则新数组就是原数组的前面 length 个元素，如果 length 大于 original 数组的长度，则新数组的前面元索就是原数组的所有元素，后面补充 0（数值类型）、false（布尔类型）或者 null（引用类型）。

**4）type[] copyOfRange(type[] original, int from, int to)**

这个方法与前面方法相似，但这个方法只复制 original 数组的 from 索引到 to 索引的元素。

**5）boolean equals(type[] a, type[] a2)**

如果 a 数组和 a2 数组的长度相等，而且 a 数组和 a2 数组的数组元素也一一相同，该方法将返回 true。

**6）void fill(type[] a, type val)**

该方法将会把 a 数组的所有元素都赋值为 val。

**7）void fill(type[] a, int fromIndex, int toIndex, type val)**

该方法与前一个方法的作用相同，区别只是该方法仅仅将 a 数组的 fromIndex 到 toIndex 索引的数组元素赋值为 val。

**8）void sort(type[] a)**

该方法对 a 数组的数组元素进行排序。

**9）void sort(type[] a, int fromIndex, int toIndex)**

该方法与前一个方法相似，区别是该方法仅仅对 fromIndex 到 toIndex 索引的元素进行排序。

**10）String toString(type[] a)**

该方法将一个数组转换成一个字符串。该方法按顺序把多个数组元素连缀在一起，多个数组元素使用英文逗号`,`和空格隔开。

 下面程序示范了 Arrays 类的用法。 

```java
public class Example03 {
    public static void main(String[] args) {
        //定义一个a数组
        int[] a = new int[]{1,2,3,4,5};
        //定义一个a2数组
        int[] a2 = new int[]{1,2,3,4,5};
        //a数组和a2数组长度相等，每个元素一次相等，将输出true
        System.out.println("a数组和a2数组是否相等"+ Arrays.equals(a,a2));
        //通过复制a数组，生成一个新的b数组
        int[] b = Arrays.copyOf(a,6);
        System.out.println("a数组和b数组长度是否相等"+Arrays.equals(a,b));
        //将b数组第3个元素（包括）到第5个元素（不包括）赋值为1
        Arrays.fill(b,2,4,1);
        //输出b数组的以元素，将输出[1, 2, 1, 1, 5, 0]
        System.out.println("b数组的元素为"+Arrays.toString(b));
        //对b数组进行排序
        Arrays.sort(b);
        //输出b数组的元素[0, 1, 1, 1, 2, 5]
        System.out.println("b数组的元素位"+Arrays.toString(b));
    }
}
```

运行结果如下：

![1655339572989](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-107.png)













































































































# 聚合操作







# Java中的常用类

# String类与StringBuffer类

Java定义了String和StringBuffer两个类来封装字符串，并提供了一系列操作字符串的方法。

## String类的初始化

在操作String类之前，首先需要对String类进行初始化。在Java中，可以通过以下两种方式对String类进行初始化，具体如下：

1).使用自负床常量直接初始化一个String对象，其语法格式如下：

```java
String 变量名 = 字符串;
```

在初始化字符串对象时，既可以将字符串对象的初始化值设为空，也可以初始化为一个具体的字符串，其示例如下：

```java
String str1 = null;     //初始化为空
String str2 = "";       //初始化位空字符串
String str3 = "abc";    //初始化为abc，其中abc为字符串常量
```

2).使用String的构造方法初始化字符串对象，其语法格式如下：

```java
String 变量名 = new String（字符串）
```

在上述语法中，字符串同样可以为空或是一个具体的字符串。当为具体的字符串时，会使用String类的不同参数类型的构造方法来初始化字符串对象。

String类中包含多个构造方法，常用的构造方法如下表

|       方法声明       |           功能描述           |
| :------------------: | :--------------------------: |
|      String( )       |   创建一个内容为空的字符串   |
| String(String value) | 根据指定的字符串内容创建对象 |
| String(char[ ]value) | 根据指定的字符串数组创建对象 |

示例：

```java
public class Example01 {
    public static void main(String[] args) {
        //创建一个空的字符串
        String str1 = new String();
        //创建一个内容为abc的字符串
        String str2 = new String("abc");
        //创建一个内容为字符数组的字符串
        char[] charArray = new char[]{'A','B','C'};
        String str3 = new String(charArray);
        //输出结果
        System.out.println("a"+str1+"b");
        System.out.println(str2);
        System.out.println(str3);
    }
}
```

运行结果如下：

![1655340436872](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-108.png)

## String类常见操作

### 1.字符串的基本操作

> 在程序中，需要对字符串进行一些基本操作，如**获得字符串长度、 获得指定位置的字符**等。

示例：

```java
public class Example02 {
    public static void main(String[] args) {
        String str = "abcabcabcabc";     //初始化字符串
        System.out.println("字符串的长度为："+str.length());
        System.out.println("字符串中第一个字符："+str.charAt(0));
        System.out.println("字符c第一次出现的位置："+str.indexOf('c'));
        System.out.println("字符c最后一次出现的位置："+str.lastIndexOf('c'));
        System.out.println("子字符串第一次出现的位置："+str.indexOf("ab"));
        System.out.println("子字符串最后一次出现的位置："+str.lastIndexOf("ab"));
    }
}
```

运行结果如下：

![1655341046147](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-109.png)

### 2.字符串的转换操作

> 程序开发中，经常需要对字符串进行转换操作，例如**将字符串转换为字符数组，将字符串中的字符进行大小写转换等**。

示例：

```java
public class Example03 {
    public static void main(String[] args) {
        String str = "java";
        char[] charArray = str.toCharArray();       //字符串转换为字符数组
        System.out.println("将字符串转为字符数组的遍历结果：");
        for (int i = 0;i<charArray.length;i++){
            if (i != charArray.length-1){
                //如果不是数组的最后一个元素，在原始后面加逗号
                System.out.print(charArray[i]+",");
            }else {
                //数组的最后一个元素后面不加逗号
                System.out.println(charArray[i]);
            }
        }
        System.out.println("将int值转换为String类型之后的结果："+String.valueOf(12));
        System.out.println("将字符串转换为大写之后的结果："+str.toUpperCase());
    }
}
```

运行结果如下：

![1655341485196](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-110.png)

### 3.字符串的替换和去除空格操作

> 在开发程序的过程中，需要考虑到用户输入数据时会有一些错误和空格的情况，这是可以使用String类的replace()和trim()方法，进行字符串的替换和去除空格操作。

示例：

```java
public class Example04 {
    public static void main(String[] args) {
        String url = "    http://localhost : 8080       ";
        //字符串去除空格操作
        System.out.println("去除字符串两端空格后的结果:"+url.trim());
        //字符串替换操作
        System.out.println("去掉字符串中所有空格后的结果："+url.replace(" ",""));
    }
}
```

运行结果如下：

![1655342501840](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-111.png)

### 4.字符串的判断操作

> 操作字符时，经常需要对字符串进行一些判断，如判断字符串是否以指定的字符串开始、结束，是否包含指定的字符串，字符串是否为空等

示例：

```java
public class Example05 {
    public static void main(String[] args) {
        String s1 = "Starter";          //声明一个字符串
        String s2 = "St";
        System.out.println("判断是否以字符串St开头："+s1.startsWith("St"));
        System.out.println("判断是否以字符串er结尾："+s1.endsWith("er"));
        System.out.println("判断是否包含字符串ar："+s1.contains("ar"));
        System.out.println("判断字符串是否为空："+s1.isEmpty());
        System.out.println("判断两个字符串是否相等："+s1.equals(s2));
    }
}
```

运行结果如下：

![1655342856065](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-112.png)

### 5.字符串的截取和分割

> 在String类中针对字符串的截取和分割操作提供了两个方法，其中，substring()方法用于截取字符串的一部分，split()方法可以将字符串按照某个字符进行分割。

示例：

```java
public class Example06 {
    public static void main(String[] args) {
        String str = "2022-06-16";
        //下面是字符串截取操作
        System.out.println("从第6个字符串截取到末尾的结果："+str.substring(5));
        System.out.println("从第6个字符串截取到第7个字符的结果："+str.substring(5,7));
        //下面是字符串分割的操作
        System.out.println("=======字符串分割的操作==========");
        System.out.println("分割后的字符串数组中的元素依次为：");
        //通过横线连接字符”-“将字符串转换为字符串数组
        String[] strArray = str.split("-");
        //循环输出数组中的元素
        for (int i = 0;i<strArray.length;i++){
            if (i!=strArray.length-1){
                //如果不是数组的最后一个元素，在元素后面加顿号
                System.out.print(strArray[i]+",");
            }else {
                //数组的最后一个元素不加顿号
                System.out.println(strArray[i]);
            }
        }
    }
}
```

运行结果如下：

![1655343396315](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\Java-113.png)

## StringBuffer类

































# System类与Runtime类









# Math类与Random类







# 包装类

 





# 日期与时间类







# 格式化类









# IO流

# 文件

## 什么是文件

文件，对我们并不陌生，文件是保存数据的地方，比如大家经常使用的wod文档，txt文件，exce文件..都是文件。它既可以保存一张图片，也可以保持视频，声音.

## 文件流

文件在程序中是以`流`的形式来操作的

![1655426119676](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-1.png)

- 流：数据在**数据源（文件）和程序（内存）**之间经历的路径
- 输入流：数据从**数据源（文件）到程序（内存）**的路径
- 输出流：数据从**程序（内存）到数据源（文件）**的路径

## 常用的文件操作 

### 创建文件对象相关构造器和方法

相关方法：

- new File(String pathname)	              //根据路径创建一个File对象
- new File(File parent,String child)        //根据父目录文件+子路径构建
- new File(String parent,String child)    //根据父目录+子路径构建

![1655427345993](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-2.png)

### 创建文件案例

在E盘下创建news1.txt、news2.txt、news3.txt文件（用三种不同方式创建）

```java
public class FileCreate {
    //方式一:new File(String pathname)
    @Test
    public void create01(){
        //创建文件的路径
        String filePath = "e:\\news1.txt";
        File file = new File(filePath);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    //方式二：new File(File parent,String child)
    //e:\\news2.txt
    @Test
    public void create02(){
        File parentFile = new File("e:\\");
        String fileName = "news2.txt";
        File file = new File(parentFile,fileName);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    //方式三：new File(String parent,String child)
    @Test
    public void create03(){
        String parent = "e:\\";
        String child = "news3.txt";
        File file = new File(parent,child);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

运行结果：

![1655427569140](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-3.png)

### 获取文件的相关信息 

> getName、getAbsolutePath、getParent、length、exists、isFile、isDirectory

![1655427975321](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-4.png)

**应用案例演示 FileInformation.java**

演示：如何获取到文件的大小，文件名，路径，父File,是文件还是目录（目录本质也是文件，一种特殊的文件)，是否存在。

```java
public class FileInformation {
    public static void main(String[] args) {
        //获取文件的信息getName、getAbsolutePath、getParent、length、exists、isFile、isDirectory
        //创建文件对象
        File file = new File("e:\\news1.txt");
        //调用相应的方法，得到相应信息
        System.out.println("文件的名字="+file.getName());
        System.out.println("文件的绝对路径="+file.getAbsolutePath());
        System.out.println("文件的父级目录="+file.getParent());
        System.out.println("文件的大小(字节)="+file.length());
        System.out.println("文件是否存在="+file.exists());
        System.out.println("是不是一个文件="+file.isFile());
        System.out.println("是不是一个目录="+file.isDirectory());
    }
}
```

运行结果如下：

![1655428465773](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-5.png)

























# IO 流原理及流的分类 

## IO 流原理

1. I/O是Input/Output的缩写，I/O技术是非常实用的技术，用于处理数据传输，如：读/写文件、网络通讯等
2. Java程序中，对于数据的输入/输出操作以“流（Stream）”的方式进行
3. java.io包下提供了各种"流"类和接口，用以获取不同种类的数据，并通过方法输入或输出数据
4. 输入input：读取外部数据（磁盘、光盘等存储设备的数据）到程序（内存）中
5. 输出output：将程序（内存）数据输出到磁盘、光盘等存储设备中

## 流的分类

- 按操作数据单位不同分为：字节流、字符流
- 按数据流的流向不同分为：输入流、输出流
- 按流的角色的不同分为：节点流，处理流/包装流

| （抽象基类） |   字节流    | 字符流 |
| :----------: | :---------: | :----: |
|    输入流    | InputSteam  | Reader |
|    输出流    | OutputSteam | Writer |

## IO 流体系图-常用的类 

**IO 流体系图** 

![JAVA之IO流](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-6.png)

## IntputStream

`IntputStream`是Java标准库提供的输入流。它位于`java.io`这个包里。

IntputStream常用方法

| 方法声明                            | 功能描述                                                     |
| :---------------------------------- | :----------------------------------------------------------- |
| int read( )                         | 从输入流读取一个8位的字节，把它转成0~255之间的整数，并返回这一整数。当没有可用字段时，将返回-1 |
| int read(byte[ ] b)                 | 从输入流读取若干字节，把它们保存到参数b指定的字节数组中，返回的整数表示读取字节的数目 |
| int read(byte[ ] b,int off,int len) | 从输入流读取若干字节，把它们保存到参数b指定的字节数组中,off指定字节数组开始保存数据的起始下标，len表示读取的字节数目 |
| void close                          | 关闭此输入流并释放与该流关联的所有系统资源                   |

::: info 解析

`前三个read( )方法都是用来读取数据的`，其中，**第一个read( )方法是从输入流逐个读入字节**，**而第二个和第三个read( )方法则将若干个字节以字节数组的形式一次性读入**，从而提高读数据的效率。而在进行I/O流操作时，当前I/O流会占用一定的内存，由于系统资源宝贵，因此，**在I/O操作结束后，应该调用close( )方法关闭流**，从而释放当前I/O流所占的系统资源。

:::

## OutputStream

`OutputStream`是 Java标准库提供的输出流。 

OutputStream常用方法

| 方法声明                              | 功能描述                                             |
| ------------------------------------- | :--------------------------------------------------- |
| void write(int b)                     | 向输出流写入一个字节                                 |
| void write(byte[ ] b)                 | 把参数b指定的字节数组的所有字节写到输出流            |
| void write(byte[ ] b,int off,int len) | 将指定byte数组中从偏移量off开始的len个字节写入输出流 |
| void flush( )                         | 刷新此输出流并强制写出所有缓冲的输出字节             |
| void close( )                         | 关闭此输出流并释放与此流相关的所有系统资源           |

::: info 解析

`前三个是重载的write( )方法，都用于向输出流写入字节`,第一个方法逐个写入字节，后两个方法是将若干个字节以字节数组的形式一次性写入，从而提高写数据的效率。flush( )方法用来将当前输出流缓冲区（通常是字节数组）中的数据强制写入目标设备，此过程称为刷新.close( )方法是用来关闭并释放与此流相关的所有系统资源。

:::

::: details  为什么要有`flush()`？ 

为什么要有`flush()`？因为向磁盘、网络写入数据的时候，出于效率的考虑，操作系统并不是输出一个字节就立刻写入到文件或者发送到网络，而是把输出的字节先放到内存的一个缓冲区里（本质上就是一个`byte[]`数组），等到缓冲区写满了，再一次性写入文件或者网络。对于很多IO设备来说，一次写一个字节和一次写1000个字节，花费的时间几乎是完全一样的，所以`OutputStream`有个`flush()`方法，能强制把缓冲区内容输出。

通常情况下，我们不需要调用这个`flush()`方法，因为缓冲区写满了`OutputStream`会自动调用它，并且，在调用`close()`方法关闭`OutputStream`之前，也会自动调用`flush()`方法。

但是，在某些情况下，我们必须手动调用`flush()`方法。举个栗子：

小明正在开发一款在线聊天软件，当用户输入一句话后，就通过`OutputStream`的`write()`方法写入网络流。小明测试的时候发现，发送方输入后，接收方根本收不到任何信息，怎么肥四？

原因就在于写入网络流是先写入内存缓冲区，等缓冲区满了才会一次性发送到网络。如果缓冲区大小是4K，则发送方要敲几千个字符后，操作系统才会把缓冲区的内容发送出去，这个时候，接收方会一次性收到大量消息。

解决办法就是每输入一句话后，立刻调用`flush()`，不管当前缓冲区是否已满，强迫操作系统把缓冲区的内容立刻发送出去。

实际上，`InputStream`也有缓冲区。例如，从`FileInputStream`读取一个字节时，操作系统往往会一次性读取若干字节到缓冲区，并维护一个指针指向未读的缓冲区。然后，每次我们调用`int read()`读取下一个字节时，可以直接返回缓冲区的下一个字节，避免每次读一个字节都导致IO操作。当缓冲区全部读完后继续调用`read()`，则会触发操作系统的下一次读取并再次填满缓冲区。

:::

## FileInputStream

>  FileInputStream流被称为文件字节输入流，意思指对文件数据以字节的形式进行读取操作如读取图片视频等 

方法摘要

![1655431767192](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-7.png)

示例：请使用 FileInputStream 读取 hello.txt 文件，并将文件内容显示到控制台

```java
public class FileInputStream01 {
    public static void main(String[] args) throws IOException {
        String filePath = "e:\\hello.txt";
        int readData = 0;
        FileInputStream fileInputStream = null;
        //字节数组
        byte[] buf = new byte[15];
        try {
            //创建FileInputStream对象，用于读取文件
            fileInputStream = new FileInputStream(filePath);
            while ((readData = fileInputStream.read(buf)) != -1){
                System.out.print(new String(buf,0, readData));
            }
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            //关闭文件流、释放资源
            fileInputStream.close();
        }
    }
}
```

运行结果如下:

![1655434185694](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-8.png)

## FileOutputStream

>  文件输出流是用于将数据写入`File`或`FileDescriptor`的输出流。 文件是否可用或是否可以创建取决于底层平台。 特别是某些平台允许一次仅打开一个文件以供写入`FileOutputStream` （或其他文件写入对象）。 在这种情况下，如果涉及的文件已经打开，则此类中的构造函数将失败。 

方法摘要

![1655434257327](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-9.png)

示例1：请使用 FileOutputStream 在 a.txt 文件，中写入 “hello，world”.写入并读取出来。

```java
public class FileOutPutStream01 {
    public static void main(String[] args) throws IOException {
        //创建FileOutPutStream 对象
        String filePath = "e:\\a.txt";
        //文件输入流
        FileOutputStream fileOutputStream = null;
        //文件输出流
        FileInputStream fileInputStream = null;
        int fileData = 0;
        try {
            //1.new FileOutputStream(filePath)      会覆盖原先内容
            //2.new FileOutputStream(filePath,true) 写入内容，追加到原内容后
            fileOutputStream = new FileOutputStream(filePath);
            fileInputStream = new FileInputStream(filePath);
            //写入单个字符
//            fileOutputStream.write('a');
            //写入字符串
            String str = "hello,world!";
            //str.getBytes("UTF-8")使用平台的默认字符集将此 String编码为字节序列，将结果存储到新的字节数组中。
            fileOutputStream.write(str.getBytes("UTF-8"));
            System.out.println("写入成功");
            System.out.println("读取数据如下：");
            while ((fileData = fileInputStream.read())!=-1){
                System.out.print((char) fileData);
            }
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } finally {
            fileOutputStream.close();
        }
    }
}
```

运行结果如下：

![1655435335274](E:\杨洲\vuepress-theme-hope\docs\.vuepress\public\images\Java\IO流\IO流-10.png)

示例2：编程完成图片/音乐 的拷贝.将`e:\\logo.png` 拷贝到d盘

::: tip 思路分析

1. 创建文件的输入流，将文件读入程序
2. 创建文件的输出流，将读取到的文件数据，写入指定的文件

:::

具体代码

```java
public class FileCopy {
    public static void main(String[] args) {
        //完成文件拷贝，将e:\\logo.png 拷贝到d盘
        //创建指定路径
        String srcPath = "e:\\logo.png";
        //创建输入路径
        String destPath = "d:\\logo.png";
        FileInputStream fileInputStream = null;
        FileOutputStream fileOutputStream = null;
        try {
            //创建FileInputStream对象，用于读取文件
            fileInputStream = new FileInputStream(srcPath);
            //创建FileOutputStream对象，用于输出文件
            fileOutputStream = new FileOutputStream(destPath);
            byte[] buffer = new byte[1024];
            int length = 0;
            while ((length = fileInputStream.read(buffer))!=-1){
                fileOutputStream.write(buffer,0,length);
            }
            System.out.println("拷贝成功~");
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            try {
                if (fileInputStream!=null){
                    fileInputStream.close();
                }
                if (fileOutputStream!=null){
                    fileOutputStream.close();
                }
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
```

运行结果：

![1655510846532](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655510846532.png)

## FileReader

>  FileReader类从InputStreamReader类继承而来。该类按字符读取流中数据 

**相关方法：**

| 方法声明                    | 功能描述                                                     |
| --------------------------- | ------------------------------------------------------------ |
| new FileReader(File/String) |                                                              |
| read()                      | 每次读取单个字符，返回该字符，如果文件末尾返回-1**           |
| read(char[ ])               | 批量读取多个字符到数组，返回读取到的字符数，如果文件末尾返回-1** |

相关API：

1. new String(char[]):将char[]转换成String
2. new String(char[],off,len):将char[]的指定部分转换成String

示例：在e盘创建文本文件”reader.txt“并在其中写入”Java基础最重要！！，不要好高骛远！！“,然后读取

**方法一：**while循环，单个字符读取

```java
public class Example01 {
    public static void main(String[] args) throws IOException {
        //创建文本文件路径
        String filePath = "e:\\reader.txt";
        //创建FileReader对象，并指定需要读取的文件
        FileReader fileReader = new FileReader(filePath);

        //定义一个int类型的变量，其初始值为0
        int len = 0;
        while((len = fileReader.read())!=-1){
            //输出读取到的字符
            System.out.print((char) len);
        }
        //关闭流
        fileReader.close();
    }
}
```

**方法二：**字符数组读取文件

```java
public class Example01 {
    public static void main(String[] args) throws IOException {
        //创建文本文件路径
        String filePath = "e:\\reader.txt";
        //创建FileReader对象，并指定需要读取的文件
        FileReader fileReader = new FileReader(filePath);
        int len = 0;
        char[] buf = new char[1024];
        while ((len = fileReader.read(buf))!=-1){
            System.out.println(new String(buf,0,len));
        }
        //关闭流
        fileReader.close();
    }
}
```

运行结果如下：

![1655512521010](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655512521010.png)

::: tip 解析

示例中，首先**创建了FileReader对象**来读取文件的内容，然后**通过while循环**每次从文件中读取一个字符并打印，这样就实现了FileReader读取文件字符的操作。由于字符输入流read( )方法**返回的是int类型的值**，如果想获得字符就需要进行强制类型转换，所有输出语句中**将变量len强转为了char类型**。

:::

## FileWriter

> FileWriter 类从 OutputStreamWriter 类继承而来。该类按字符向流中写入数据。 

常用方法：

| 方法声明                         | 功能描述                       |
| -------------------------------- | ------------------------------ |
| new FileWriter(File/String)      | 覆盖模式，如果文件末尾返回-1   |
| new FileWriter(File/String,true) | 追加模式，相当于流的指针在末端 |
| writer(int):写入单个字符         | 写入单个字符                   |
| writer(char[])                   | 写入指定数组                   |
| writer(char[],off,len)           | 写入指定数组的指定部分         |
| writer(string)                   | 写入整个字符串                 |
| writer(string,off,len)           | 写入字符串的指定部分           |

相关API：String类：toCharArray:将String转换为char[ ]

::: tip 注意

FilterWriter使用后，必须要关闭(close)或刷新(flush)，否则写入不到指定的文件!!!!

:::

示例：在”reader.txt“中写入"好好学习，天天向上;一分耕耘一分收获;你的付出会有好结果"

具体代码：

```java
public class Example02 {
    public static void main(String[] args) throws IOException {
        //创建字符输出流对象，并数值指定文件
        String filePath = "e:\\reader.txt";
        FileWriter fileWriter = new FileWriter(filePath,true);
        fileWriter.write("好好学习，天天向上\r\n");
        fileWriter.write("一分耕耘一分收获\r\n");
        fileWriter.write("你的付出会有好结果\r\n");
        System.out.println("写入成功~");
        //关闭流
        fileWriter.close();
    }
}
```

运行结果如下：

![1655513215952](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655513215952.png)

# 节点流和处理流

## 基本介绍

1.**节点流**可以从一个特定的数据源`读写数据`，如FileReader、FileWriter[源码]

![1655517074421](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655517074421.png)

2.**处理流（也叫包装流）**是"连接"在已存在的流（节点流或处理流）之上，为程序提供强大的读写功能，也更加灵活，如BufferedReader、BufferedWriter[源码]

![1655517181694](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655517181694.png)

## 节点流和处理流一览图 

![1655517678523](C:\Users\杨洲\AppData\Roaming\Typora\typora-user-images\1655517678523.png)

## 节点流和处理流的区别和联系 

1.节点流是底层流/低级流，直接跟数据源相接，
2.处理流（包装流）包装节点流，既可以消除不同节点流的实现差异，也可以提供更方便的方法来完成输入输出。[源码理解
3.处理流（也叫包装流）对节点流进行包装，使用了修饰器设计模式，不会直接与数据
源相连[**模拟修饰器设计模式]**



























# 输入流



















# 输出流





















# Properties 类 