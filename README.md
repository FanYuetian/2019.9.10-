# 2019.9.10-

一.关于default和protected的具体区别
   default拒绝一切包外访问（本包）、protected接受包外的子类访问（子类）
二.DriverManager.getConnection方法返回一个connection对象，这是加载驱动之后才能进行的
   调用class.forName、通过添加系统的jdbc.drivers属性、通过registerDriver方法注册都是加载驱动程序的方法
三.ThreadLocal类为每一个线程都维护了自己独有的变量拷贝、每个线程都拥有了自己独立的一个变量，所以ThreadLocal重要作用并不在于多线程间的数据共享，而是数据独立，变量被彻底封闭在每个访问的线程中。
   ThreadLocal中定义了一个哈希表用于为每个线程 都提供一个变量副本
四.树的深度优先搜索算法：按照某种条件往前试探搜索，如果前进中遭到失败，则退回头另选通路继续搜索，直到找到条件的目标为止；假设树的顶点数为V，则算法的空间复杂度为O(V)，深度优先算法非常适合使用递归来实现。
五.广度优先算法：先访问该节点所有的子节点，遍历完毕后选取它未访问过的子节点重复上述过程，直到找到条件目标为止
六.数据结构中结点总数=边数+1
七.逆波兰式就是后缀表达式，其求值过程可以用到栈来辅助存储：遇到数字先进栈，遇到符号弹出两个数字，运算后再进栈，直到全部弹出
八.在具有2n个结点的完全二叉树中，叶子结点个数为n
九.最小生成树代价一定是唯一的

十.applet的方法：init()、start()、stop()、destroy()
               init()：执行初始化任务
               start()：程序开始执行的方法
               stop()：停止执行，当含有该applet的web页被其他页代替时调用
               destory()：收回applet程序的所有资源、即释放已分配给它的所有资源
十一.运算
     boolean b=true?false:true==true?false:true
       boolean b=true?false: true==true ?false:true;
      =boolean b=true?false: (true==true) ?false:true;
      =boolean b=true?false:  true?false:true;
      =boolean b=true?false:  (true?false:true);
      =boolean b=true?false: false;
      =boolean b=false;
      [] ? true : false// 也就是
      if([]){
      return true;
    }else {
      return false;
    }
十二.final定义变量，不是必须要在定义的同时完成初始化，也可以在构造方法中完成初始化。
十三.重写一个线程类，可以继承thread方法，然后override他的run方法，另一种方法是实现runnable接口，就实现了run方法，start只是启动一个线程的方法

十四.n0=n2+1，含有N个叶子结点的最优二叉树中共有n-1个分支结点
十五.具有n个节点的完全二叉树的深度为log2n+1

十六.方法重载（参数表）
十七.socket套接字：源IP地址、目标IP地址、源端口号、目标端口号组合
     服务器端：serversocket提供实例serversocket server = new serversocket（端口号）
     客户端：socket SOC = new socket(ip地址,端口号)
十八.randomaccessfile可以通过seek（long POS）方法去移动文件指针进行追加更新写入
十九.switch语句后的控制表达式只能是short、char、int、long整数类型和枚举类型，不能是float、double、boolean类型。string类型是1.7开始支持

二十.内部类可以是静态static，也可以用public、default、protected、private
     外部类的修饰符只能是public、abstract、final
     static修饰的类为静态类，会随着类的加载而加载，如果没有使用过这个类加载就会浪费内存。
二十二.list：有序，可以放重复数据；ArrayList是数组，适合查询，不适合增删；linkedlist是双向链表，适合增删，不适合查询；vector是数组，线程安全，效率较低
      set：无序，不允许重复；hashset是哈希表/散列表；treeset会按照存入元素大小自动排序
      map：无序，以键值对存放，键不能重复，值可以重复；hashmap不同步，线程不安全；hashtable线程安全；hashmap中的key-value都存放在entry中；hashmap可以存Null值和null键，通过hashcode和equals方法保证键的唯一性
二十三.volatile不保证对变量操作的原子性，只能包装可见性
二十四.for(m=0,n=-1;n=0;m++,n++){
            n++;
       }//for循环的借宿判定条件是Boolean型for(初始化语句;判断条件语句;控制条件语句)
二十五.public Method[] getDeclaredMethods()返回类或接口声明的所有方法，包括所有修饰符，但不包括继承方法，包括所实现接口的方法
二十六.public Method[] getMethods()返回类的所有public方法，包括继承类的公用方法，当然也包括它所有实现的接口方法
二十七.throw用于抛出异常、throws可以在方法上声明该方法抛出的异常，然后在方法内部通过throw抛出异常对象
二十八.垃圾回收机制：
      1.新生代：（1）所有对象创建在新生代的Eden区，当Eden区满后触发新生代的minorGC，将Eden区和非空闲survivor区存活的对象复制到另外一个空闲的survivor区中
               （2）保证一个survivor区是空的，新生代minorGC就是在两个survivor区之间相互复制存活对象，直到survivor区满为止
      2.老年代：当survivor区也满之后就通过minorGC将对象复制到老年代，老年代也满了就触发FullGC,针对整个堆（新生代、老年代、持久代）进行垃圾回收
      3.持久代：持久代如果满了，将会触发FullGC
