# Learn
  学习知识点的总结，最近发现年纪大了学习的东西总忘，而且光通过看的方式缺少总结掌握的也不深刻。面试的时候遇到很多问题因为掌握的不够深，回答的也不好，
直接影响到了我的致富。自己现在还很菜，可是我不想一直这么菜，我好羡慕那些大神。慢慢总结一些东西，我想赚大钱。还不知道从哪里下手。
有问题也请指教，别喷！乖
# 计算机组成原理
# 数据结构
  理了一下思路，我觉得还是从数据结构开始学起吧。上学的时候一直都不是很理解这玩意有啥用，学了能干啥。 现在看来代码写不好或者写出来的东西不是人看的有很多
  情况下是因为数据结构没有掌握好，***数据结构是编程的基础！*** 在我看来，数据结构更像是一种容器，每一种容器里可以容纳同一类型的数据，每个容器又有自己的
  独特的规则。如果我们开发人员是战场上的士兵，每一种数据结构对抗的是我们面对敌人（需求）的武器，单向链表（武器：铁链）、循环链表（武器:铁链组成的圆环）、
  算了，编的太累。直接干的。
  ## 1. 线性表
  
# 计算机网络
# Java基础
 ## 1.枚举类
 https://www.cnblogs.com/sister/p/4700702.html
 一、什么情况下使用枚举类？

　　有的时候一个类的对象是有限且固定的，这种情况下我们使用枚举类就比较方便？

二、为什么不用静态常量来替代枚举类呢？

    public static final int SEASON_SPRING = 1;
    public static final int SEASON_SUMMER = 2;
    public static final int SEASON_FALL = 3;
    public static final int SEASON_WINTER = 4;
　　枚举类更加直观，类型安全。使用常量会有以下几个缺陷：

　　1. 类型不安全。若一个方法中要求传入季节这个参数，用常量的话，形参就是int类型，开发者传入任意类型的int类型值就行，但是如果是枚举类型的话，就只能传入枚举类中包含的对象。

　　2. 没有命名空间。开发者要在命名的时候以SEASON_开头，这样另外一个开发者再看这段代码的时候，才知道这四个常量分别代表季节。

三、枚举类入门

　　先看一个简单的枚举类。

package enumcase;

public enum SeasonEnum {
    SPRING,SUMMER,FALL,WINTER;
}
enum和class、interface的地位一样
使用enum定义的枚举类默认继承了java.lang.Enum，而不是继承Object类。枚举类可以实现一个或多个接口。
枚举类的所有实例都必须放在第一行展示，不需使用new 关键字，不需显式调用构造器。自动添加public static final修饰。
使用enum定义、非抽象的枚举类默认使用final修饰，不可以被继承。
枚举类的构造器只能是私有的。
四、枚举类介绍

　　枚举类内也可以定义属性和方法，可是是静态的和非静态的。

复制代码
package enumcase;

public enum SeasonEnum {
    SPRING("春天"),SUMMER("夏天"),FALL("秋天"),WINTER("冬天");
    
    private final String name;
    
    private SeasonEnum(String name)
    {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}
复制代码
 　  实际上在第一行写枚举类实例的时候，默认是调用了构造器的，所以此处需要传入参数，因为没有显式申明无参构造器，只能调用有参数的构造器。

　　构造器需定义成私有的，这样就不能在别处申明此类的对象了。枚举类通常应该设计成不可变类，它的Field不应该被改变，这样会更安全，而且代码更加简洁。所以我们将Field用private final修饰。

五、枚举类实现接口

　　枚举类可以实现一个或多个接口。与普通类一样，实现接口的时候需要实现接口中定义的所有方法，若没有完全实现，那这个枚举类就是抽象的，只是不需显式加上abstract修饰，系统化会默认加上。

　　

复制代码
package enumcase;

public enum Operation {
    PLUS{

        @Override
        public double eval(double x, double y) {
            return x + y;
        }
        
    },
    MINUS{

        @Override
        public double eval(double x, double y) {
            return x - y;
        }
        
    },
    TIMES{

        @Override
        public double eval(double x, double y) {
            return x * y;
        }
        
    },
    DIVIDE{

        @Override
        public double eval(double x, double y) {
            return x / y;
        }
        
    };
    
    /**
     * 抽象方法，由不同的枚举值提供不同的实现。
     * @param x
     * @param y
     * @return
     */
    public abstract double eval(double x, double y);
    
    public static void main(String[] args) {
        System.out.println(Operation.PLUS.eval(10, 2));
        System.out.println(Operation.MINUS.eval(10, 2));
        System.out.println(Operation.TIMES.eval(10, 2));
        System.out.println(Operation.DIVIDE.eval(10, 2));
    }
}
复制代码
　　Operatio类实际上是抽象的，不可以创建枚举值，所以此处在申明枚举值的时候，都实现了抽象方法，这其实是匿名内部类的实现，花括号部分是一个类体。我们可以看下编译以后的文件。

　　

　　共生成了五个class文件，这样就证明了PLUS,MINUS,TIMES,DIVIDE是Operation的匿名内部类的实例。

六、switch语句里的表达式可以是枚举值

　　Java5新增了enum关键字，同时扩展了switch。

复制代码
package enumcase;

public class SeasonTest {
    public void judge(SeasonEnum s)
    {
        switch(s)
        {
        case SPRING:
            System.out.println("春天适合踏青。");
            break;
        case SUMMER:
            System.out.println("夏天要去游泳啦。");
            break;
        case FALL:
            System.out.println("秋天一定要去旅游哦。");
            break;
        case WINTER:
            System.out.println("冬天要是下雪就好啦。");
            break;
        }
    }
    
    public static void main(String[] args) {
        SeasonEnum s = SeasonEnum.SPRING;
        SeasonTest test = new SeasonTest();
        test.judge(s);
    }
}
# Java内存管理
# Java并发编程
# 常用WEB开发框架
# 数据库
# 分布式
# 中间件
# 常用算法
# LeetCode

