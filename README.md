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
  ## 2、二叉树
一、树的定义

树是一种数据结构，它是由n（n>=1）个有限结点组成一个具有层次关系的集合。

 ![](https://img-blog.csdn.net/20170324154348019)

树具有的特点有：

（1）每个结点有零个或多个子结点

（2）没有父节点的结点称为根节点

（3）每一个非根结点有且只有一个父节点

（4）除了根结点外，每个子结点可以分为多个不相交的子树。

 

树的基本术语有：

若一个结点有子树，那么该结点称为子树根的“双亲”，子树的根称为该结点的“孩子”。有相同双亲的结点互为“兄弟”。一个结点的所有子树上的任何结点都是该结点的后裔。从根结点到某个结点的路径上的所有结点都是该结点的祖先。

 

结点的度：结点拥有的子树的数目

叶子结点：度为0的结点

分支结点：度不为0的结点

树的度：树中结点的最大的度

层次：根结点的层次为1，其余结点的层次等于该结点的双亲结点的层次加1

树的高度：树中结点的最大层次

森林：0个或多个不相交的树组成。对森林加上一个根，森林即成为树；删去根，树即成为森林。

 

二、二叉树

1、二叉树的定义

二叉树是每个结点最多有两个子树的树结构。它有五种基本形态：二叉树可以是空集；根可以有空的左子树或右子树；或者左、右子树皆为空。
 ![]( https://img-blog.csdn.net/20170324154426661)

2、二叉树的性质

性质1：二叉树第i层上的结点数目最多为2i-1(i>=1)

性质2：深度为k的二叉树至多有2k-1个结点（k>=1）

性质3：包含n个结点的二叉树的高度至少为(log2n)+1

性质4：在任意一棵二叉树中，若终端结点的个数为n0，度为2的结点数为n2，则n0=n2+1

 

3、性质4的证明

性质4：在任意一棵二叉树中，若终端结点的个数为n0，度为2的结点数为n2，则n0=n2+1

证明：因为二叉树中所有结点的度数均不大于2，不妨设n0表示度为0的结点个数，n1表示度为1的结点个数，n2表示度为2的结点个数。三类结点加起来为总结点个数，于是便可得到：n=n0+n1+n2 (1)

由度之间的关系可得第二个等式：n=n0*0+n1*1+n2*2+1即n=n1+2n2+1 (2)

将（1）（2）组合在一起可得到n0=n2+1

 

三、满二叉树、完全二叉树和二叉查找树

1、满二叉树

定义：高度为h，并且由2h-1个结点组成的二叉树，称为满二叉树

 ![](https://img-blog.csdn.net/20170324154449411)



2、完全二叉树

定义：一棵二叉树中，只有最下面两层结点的度可以小于2，并且最下层的叶结点集中在靠左的若干位置上，这样的二叉树称为完全二叉树。

特点：叶子结点只能出现在最下层和次下层，且最下层的叶子结点集中在树的左部。显然，一棵满二叉树必定是一棵完全二叉树，而完全二叉树未必是满二叉树。

 
![](https://img-blog.csdn.net/20170324154512412)


面试题：如果一个完全二叉树的结点总数为768个，求叶子结点的个数。

由二叉树的性质知：n0=n2+1，将之带入768=n0+n1+n2中得：768=n1+2n2+1，因为完全二叉树度为1的结点个数要么为0，要么为1，那么就把n1=0或者1都代入公式中，很容易发现n1=1才符合条件。所以算出来n2=383，所以叶子结点个数n0=n2+1=384。

总结规律：如果一棵完全二叉树的结点总数为n，那么叶子结点等于n/2（当n为偶数时）或者(n+1)/2（当n为奇数时）

 

3、二叉查找树

定义：二叉查找树又被称为二叉搜索树。设x为二叉查找树中的一个结点，x结点包含关键字key，结点x的key值计为key[x]。如果y是x的左子树中的一个结点，则key[y]<=key[x]；如果y是x的右子树的一个结点，则key[y]>=key[x]

 ![](https://img-blog.csdn.net/20170324154539151)





在二叉查找树种：

（1）若任意结点的左子树不空，则左子树上所有结点的值均小于它的根结点的值。

（2）任意结点的右子树不空，则右子树上所有结点的值均大于它的根结点的值。

（3）任意结点的左、右子树也分别为二叉查找树。

（4）没有键值相等的结点。


原文：https://blog.csdn.net/xiaoquantouer/article/details/65631708 

		
	
	
		

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
        public double eval(double x, double y) 
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

