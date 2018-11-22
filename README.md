# JDK源码相关  
  JDK源码【1.7/1.8/1.9】，方便查看代码；  
  Java官方demo。


  JDK源码【1.9】，模块化系统、JShell、集合工厂方法等 


# 学习设计模式过程中总结的jdk中相关的设计模式

Structural（结构模式）
Adapter:
把一个接口或是类变成另外一种。

    * java.util.Arrays#asList()
    * javax.swing.JTable(TableModel)
    * java.io.InputStreamReader(InputStream)
    * java.io.OutputStreamWriter(OutputStream)
    * javax.xml.bind.annotation.adapters.XmlAdapter#marshal()
    * javax.xml.bind.annotation.adapters.XmlAdapter#unmarshal()

Bridge:
把抽象和实现解藕，于是接口和实现可在完全独立开来。

    * AWT (提供了抽象层映射于实际的操作系统)
    * JDBC

Composite:
让使用者把单独的对象和组合对象混用。

    * javax.swing.JComponent#add(Component)
    * java.awt.Container#add(Component)
    * java.util.Map#putAll(Map)
    * java.util.List#addAll(Collection)
    * java.util.Set#addAll(Collection)

Decorator:
为一个对象动态的加上一系列的动作，而不需要因为这些动作的不同而产生大量的继承类。这个模式在JDK中几乎无处不在，所以，下面的列表只是一些典型的。

    * java.io.BufferedInputStream(InputStream)
    * java.io.DataInputStream(InputStream)
    * java.io.BufferedOutputStream(OutputStream)
    * java.util.zip.ZipOutputStream(OutputStream)
    * java.util.Collections#checked[List|Map|Set|SortedSet|SortedMap]()

Facade:
用一个简单的接口包状一组组件，接口，抽象或是子系统。

    * java.lang.Class
    * javax.faces.webapp.FacesServlet

Flyweight:
有效率地存储大量的小的对象。

    * java.lang.Integer#valueOf(int)
    * java.lang.Boolean#valueOf(boolean)
    * java.lang.Byte#valueOf(byte)
    * java.lang.Character#valueOf(char)

Proxy:
用一个简单的对象来代替一个复杂的对象。

    * java.lang.reflect.Proxy
    * RMI

Creational（创建模式）
Abstract factory:
创建一组有关联的对象实例。这个模式在JDK中也是相当的常见，还有很多的framework例如Spring。我们很容易找到这样的实例。

    * java.util.Calendar#getInstance()
    * java.util.Arrays#asList()
    * java.util.ResourceBundle#getBundle()
    * java.sql.DriverManager#getConnection()
    * java.sql.Connection#createStatement()
    * java.sql.Statement#executeQuery()
    * java.text.NumberFormat#getInstance()
    * javax.xml.transform.TransformerFactory#newInstance()

Builder:
主要用来简化一个复杂的对象的创建。这个模式也可以用来实现一个 Fluent Interface。

    * java.lang.StringBuilder#append()
    * java.lang.StringBuffer#append()
    * java.sql.PreparedStatement
    * javax.swing.GroupLayout.Group#addComponent()

Factory:
简单来说，按照需求返回一个类型的实例。

    * java.lang.Proxy#newProxyInstance()
    * java.lang.Object#toString()
    * java.lang.Class#newInstance()
    * java.lang.reflect.Array#newInstance()
    * java.lang.reflect.Constructor#newInstance()
    * java.lang.Boolean#valueOf(String)
    * java.lang.Class#forName()

Prototype:
使用自己的实例创建另一个实例。有时候，创建一个实例然后再把已有实例的值拷贝过去，是一个很复杂的动作。所以，使用这个模式可以避免这样的复杂性。

    * java.lang.Object#clone()
    * java.lang.Cloneable

Singleton:
只允许一个实例。在 Effective Java中建议使用Emun.

    * java.lang.Runtime#getRuntime()
    * java.awt.Toolkit#getDefaultToolkit()
    * java.awt.GraphicsEnvironment#getLocalGraphicsEnvironment()
    * java.awt.Desktop#getDesktop()

Behavioral(行为模式)

Chain of responsibility:
把一个对象在一个链接传递直到被处理。在这个链上的所有的对象有相同的接口（抽象类）但却有不同的实现。

    * java.util.logging.Logger#log()
    * javax.servlet.Filter#doFilter()

Command:
把一个或一些命令封装到一个对象中。

    * java.lang.Runnable
    * javax.swing.Action

Interpreter:
一个语法解释器的模式。

    * java.util.Pattern
    * java.text.Normalizer
    * java.text.Format

Iterator:
提供一种一致的方法来顺序遍历一个容器中的所有元素。

    * java.util.Iterator
    * java.util.Enumeration

Mediator:
用来减少对象单的直接通讯的依赖关系。使用一个中间类来管理消息的方向。

    * java.util.Timer
    * java.util.concurrent.Executor#execute()
    * java.util.concurrent.ExecutorService#submit()
    * java.lang.reflect.Method#invoke()

Memento:
给一个对象的状态做一个快照。Date类在内部使用了一个long型来做这个快照。

    * java.util.Date
    * java.io.Serializable

Null Object:
这个模式用来解决如果一个Collection中没有元素的情况。

    * java.util.Collections#emptyList()
    * java.util.Collections#emptyMap()
    * java.util.Collections#emptySet()

Observer:
允许一个对象向所有的侦听的对象广播自己的消息或事件。

    * java.util.EventListener
    * javax.servlet.http.HttpSessionBindingListener
    * javax.servlet.http.HttpSessionAttributeListener
    * javax.faces.event.PhaseListener

State:
这个模式允许你可以在运行时很容易地根据自身内部的状态改变对象的行为。

    * java.util.Iterator
    * javax.faces.lifecycle.LifeCycle#execute()

Strategy:
定义一组算法，并把其封装到一个对象中。然后在运行时，可以灵活的使用其中的一个算法。

    * java.util.Comparator#compare()
    * javax.servlet.http.HttpServlet
    * javax.servlet.Filter#doFilter()

Template method:
允许子类重载部分父类而不需要完全重写。

    * java.util.Collections#sort()
    * java.io.InputStream#skip()
    * java.io.InputStream#read()
    * java.util.AbstractList#indexOf()

Visitor:

作用于某个对象群中各个对象的操作. 它可以使你在不改变这些对象本身的情况下,定义作用于这些对象的新操作.

    * javax.lang.model.element.Element 和javax.lang.model.element.ElementVisitor
    * javax.lang.model.type.TypeMirror 和javax.lang.model.type.TypeVisitor
    
    
    
很多java开发的小伙伴都会阅读jdk源码，然而确不知道应该从哪读起。以下为小编整理的通常所需阅读的源码范围。
标题为包名，后面序号为优先级1-4，优先级递减
1、java.lang

1) Object 1
2) String 1
3) AbstractStringBuilder 1
4) StringBuffer 1
5) StringBuilder 1
6) Boolean 2
7) Byte 2
8) Double 2
9) Float 2
10) Integer 2
11) Long 2
12) Short 2
13) Thread 2
14) ThreadLocal 2
15) Enum 3
16) Throwable 3
17) Error 3
18) Exception 3
19) Class 4
20) ClassLoader 4
21) Compiler 4
22) System 4
23) Package 4
24) Void 4

2、java.util

1) AbstractList 1
2) AbstractMap 1
3) AbstractSet 1
4) ArrayList 1
5) LinkedList 1
6) HashMap 1
7) Hashtable 1
8) HashSet 1
9) LinkedHashMap 1
10) LinkedHashSet 1
11) TreeMap 1
12) TreeSet 1
13) Vector 2
14) Queue 2
15) Stack 2
16) SortedMap 2
17) SortedSet 2
18) Collections 3
19) Arrays 3
20) Comparator 3
21) Iterator 3
22) Base64 4
23) Date 4
24) EventListener 4
25) Random 4
26) SubList 4
27) Timer 4
28) UUID 4
29) WeakHashMap 4

3、java.util.concurrent

1) ConcurrentHashMap 1
2) Executor 2
3) AbstractExecutorService 2
4) ExecutorService 2
5) ThreadPoolExecutor 2
6) BlockingQueue 2
7）AbstractQueuedSynchronizer 2
8）CountDownLatch 2
9) FutureTask 2
10）Semaphore 2
11）CyclicBarrier 2
13）CopyOnWriteArrayList 3
14）SynchronousQueue 3
15）BlockingDeque 3
16) Callable 4

4、java.util.concurrent.atomic

1) AtomicBoolean 2
2) AtomicInteger 2
3) AtomicLong 2
4) AtomicReference 3

5、java.lang.reflect

1) Field 2
2) Method 2

6、java.lang.annotation

1) Annotation 3
2) Target 3
3) Inherited 3
4) Retention 3
5) Documented 4
6) ElementType 4
7) Native 4
8) Repeatable 4

7、java.util.concurrent.locks

1) Lock 2
2) Condition 2
3) ReentrantLock 2
4) ReentrantReadWriteLock 2

8、java.io

1) File 3
2) InputStream   3
3) OutputStream  3
4) Reader  4
5) Writer  4

9、java.nio

1) Buffer 3
2) ByteBuffer 4
3) CharBuffer 4
4) DoubleBuffer 4
5) FloatBuffer 4
6) IntBuffer 4
7) LongBuffer 4
8) ShortBuffer 4

10、java.sql

1) Connection 3
2) Driver 3
3) DriverManager 3
4) JDBCType 3
5) ResultSet 4
6) Statement 4

11、java.net

1) Socket 3
2) ServerSocket 3
3) URI 4
4) URL 4
5) URLEncoder 4

阅读笔记简版

1、Object
1) wait(), notify(), notifyAll(), wait(timeout)
2) hashCode(), equals()
3) clone()

2、String
1) char[] value
2) int hash
3) equals(), startWith(), endWith(), replace

3、AbstractStringBuilder
1) char[] value
2) int count
3) 扩容：翻倍，不够取所需最小

4、StringBuffer
1) 继承AbstractStringBuilder
2) synchronized方法保证线程安全
3) char[] toStringCache

5、StringBuilder 继承AbstractStringBuilder

6、ArrayList
1) Object[] elementData
2) int size
3) 默认大小10
4) 扩容：翻倍，不够取所需最小

7、LinkedList
1) Node {E item, Node prev, Node next}
2) int size
3) Node first
4) Node last
5) linkFirst(), linkLast(), linkBefore(), unLinkFirst(), unLinkLast(), unLink(), indexOf()

8、HashMap
1) Node{int hash, K key, V value, Node next}
2) 默认容量16，负载因子0.75f
3) int size, modCount, threshold, float loadFactor
4) Node[] table
5) Set entrySet
6) put():根据key算hash，根据容量和hash算index，table[index]没有直接添加到数组中，table[index]有，若index位置同一个key则更新，否则遍历next是否有，有则更新，无则新增，最后根据thread与size判断是否扩容。注：扩容时容量翻倍，重新算hash复制到新数组
7）get()类似
注：先比较hash，若相等在比较equals

9、Hashtable
1) 结构实现与HashMap基本一致
2)通过synchronized方法保证线程安全

10、HashSet：委托给HashMap，其Value是同一个默认对象

11、LinkedHashMap继承HashMap
1) Entry{HashMap.Node, Entry before, after}
2) Entry head, tail
3) 重写newNode()添加节点时，除像HashMap中添加外，保存before、after信息

12、LinkedHashSet继承HashSet：不知道如何实现的顺序？

13、AbstractMap维护EntrySet，AbstractSet维护Iterator，AbstractList维护Iterator

14、ConcurrentHashMap
1) JDK1.7及以前：
a、Segment[] ,HashEntry[] , HashEntry{hash, k, v, next}
b、根据key算hash，根据hash和Segment的大小算位置，每个segment拥有一个自己的HashEntry[]
c、get()：不加锁，volatile类型
d、put(): 对相应segment加锁
e、size()：各HashEntry[] 之和，先不加锁算两遍，若一致则返回，若不一致则加锁重新计算
2）JDK1.8
a、Node{hash, key, value, next}
b、Node[] table
c、大多数操作类似于HashMap，不同CAS方式设置，根据key算hash，在根据hash和容量算index，对table[index]加锁，从而达到更大的并发量
d、get(): 同HashMap
e、put(): 对table[index]加锁

15、TreeMap
1）红黑树，即自平衡二叉查找树，时间复杂度O(logn)
2）Entry{K k, V v, Entry parent, left, right, boolean color}
3）Entry root，int size， int modeCount

16、TreeSet：委托TreeMap实现
--------------------- 
作者：猴子哥哥1024 
来源：CSDN 
原文：https://blog.csdn.net/qq_21033663/article/details/79571506 
版权声明：本文为博主原创文章，转载请附上博文链接！