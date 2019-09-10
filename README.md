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
十六.
