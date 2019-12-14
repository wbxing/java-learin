# DataStructure

## Java 的一些数据结构

### 数据结构
数据结构是计算机存储、组织数据的方式，指相互之间存在一种或多种特定关系的数据元素的集合。通常情况下，精心选择的数据结构可以带来更高的运行或者存储效率。数据结构往往同高效的检索算法和索引技术有关。

#### 数据结构的基本功能
  - 添加某一数据项
  - 删除某一特定数据项
  - 查找某一特定数据项
  - 迭代访问各个数据项
  
#### 常用数据结构
  - 数组 `Array`
  - 链表 `Linked List`
  - 栈 `Stack`
  - 队列 `Queue`
  - 树 `Tree`
  - 哈希表 `Hash Table`
  - 堆 `Heap`
  - 图 `Graph`

### 数组

#### 数组的声明
  - 第一种方式：
    > 数据类型 []  数组名称 = new 数据类型[数组长度];
  
    这里 `[]` 可以放在数组名称的前面，也可以放在数组名称的后面，
    放在前面的时候，`数据类型 []` 可以很明显地看出这是一个数组类型。
  - 第二种方式
    > 数据类型 [] 数组名称 = {数组元素1，数组元素2，......};
    
    这种方式声明数组的同时直接给定了数组的元素，
    数组的大小由 `{}` 中给定的数组元素的个数决定。            
   ```java
   // 声明数组1, 声明一个长度为3, 只能存放int类型的数据
   int [] myArray = new int[3];
   // 声明数组2, 声明一个数组元素为 1, 2, 3 的 int 类型数组
   int [] myArray2 = {1,2,3};
   ``` 

#### 访问数组元素以及给数组元素赋值 
数组是存在下标索引的，通过下标可以获取指定位置的元素，数组下标是从 `0` 开始的，也就是说下标 `0` 对应的就是数组中第 `1` 个元素，可以很方便的对数组中的元素进行存取操作。

前面声明数组的第二种方式，在声明数组的同时，也对数组进行了初始化赋值。
   ```java
   // 声明数组, 声明一个长度为 3，只能存放 int 类型的数据
   int [] myArray = new int[3];
   // 给 myArray 第一个元素赋值 1
   myArray[0] = 1;
   // 访问 myArray 的第一个元素
   System.out.println(myArray[0]);
   ```

#### 数组遍历
数组有个 `length` 属性，是记录数组的长度的，我们可以利用 `length` 属性来遍历数组。
  
```java
// 声明数组2,声明一个数组元素为 1,2,3的int类型数组
int [] myArray2 = {1,2,3};
for(int i = 0 ; i < myArray2.length ; i++){
    System.out.println(myArray2[i]);
}
```

### 链表

#### 普通链表
链表通常由一连串节点组成，每个节点包含任意的实例数据 (`data fields`)和一个或两个用来指向上一个或下一个节点的位置的链接 (`links`)链表 (`Linked list`) 是一种常见的基础数据结构，是一种线性表，但是并不会按线性的顺序存储数据，而是在每一个节点里存到下一个节点的指针 (`Pointer`) 。

使用链表结构可以克服数组链表需要预先知道数据大小的缺点，链表结构可以充分利用计算机内存空间，实现灵活的内存动态管理。但是链表失去了数组随机读取的优点，同时链表由于增加了结点的指针域，空间开销比较大。

#### 单向链表
单链表是链表中结构最简单的。一个单链表的节点 (`Node`) 分为两个部分，第一个部分 (`data`) 保存或者显示关于节点的信息，另一个部分存储下一个节点的地址。最后一个节点存储地址的部分指向空值。

单向链表只可向一个方向遍历，一般查找一个节点的时候需要从第一个节点开始每次访问下一个节点，一直访问到需要的位置。而插入一个节点，对于单向链表，我们只提供在链表头插入，只需要将当前插入的节点设置为头节点， `next` 指向原头节点即可。删除一个节点，我们将该节点的上一个节点的 `next` 指向该节点的下一个节点。

#### 双端链表
单项链表存在很多缺陷，比如如果想在尾部添加一个节点，那么必须从头部一直遍历到尾部，找到尾节点，然后在尾节点后面插入一个节点。这样的操作很麻烦，但是如果在设计链表的时候多个对尾节点的引用，这样在尾部添加节点就会简单很多，这样就形成了双端链表。

#### 有序链表
前面的链表实现插入数据都是无序的，在有些应用中需要链表中的数据有序，这称为有序链表。

#### 双向链表
在单向链表的基础上，为每一个节点增加指向前一个节点位置的连接，这样就形成了双向链表，双向链表可以从两个方向进行遍历。

### 栈
栈，又称为堆栈或堆叠，是一种只能在一端进行插入和删除操作的数据结构。栈按照先进后出的原则存储数据，先进入的数据被压入栈底，最后的数据在栈顶，需要读数据的时候从栈顶开始弹出数据（**最后一个数据被第一个读出来**）。栈具有记忆作用，对栈的插入与删除操作中，不需要改变栈底指针。

允许进行插入和删除操作的一端称为栈顶 (`top`)，另一端为栈底 (`bottom`)；栈底固定，而栈顶浮动；栈中元素个数为零时称为空栈。由于数据的操作只允许在栈的一端进行，因而按照后进先出的原理运作。所以栈也被称为后进先出表。

栈有很多应用，比如 `word` 的撤销功能，就是基于栈的。常见的有 `实现现字符串逆序` 、 `前序、中序和后序表达式的转换` 以及 `括号匹配`。

### 队列
队列是一种先进先出的数据结构

#### 单向队列
入队的一端称为队尾 (`rear`)，出队的一端称为队头 (`front`)。

#### 双端队列
双端队列就是一个两端都是结尾或者开头的队列，队列的每一端都可以进行插入数据项和移除数据。

双端队列一般提供四种方法：`insertLeft()`, `insertRight()`, `removeLeft()`, `removeRight()`

如果限制只使用 `insertLeft()` 和 `removeLeft()`，那么队列就变成了栈；如果限制只使用 `insertLeft()` 和 `removeRight()`，那么就是普通队列。

#### 优先队列
优先队列 (`priority queue`) 是比栈和队列更专用的数据结构，在优先队列中，数据项按照关键字进行排序，关键字最小（或者最大）的数据项往往在队列的最前面，而数据项在插入的时候都会插入到合适的位置以确保队列的有序。

### 递归
严格来讲递归不算是一种数据结构，而属于一种算法。递归，就是在运行的过程中调用自己。递归必须要有三个要素：
1. 边界条件
1. 递归前进段
1. 递归返回段

当边界条件不满足时，递归前进；当边界条件满足时，递归返回。

#### 递归的应用
- 求阶乘
  ```java
  /*
   * 0！=1  1！=1
   * 负数没有阶乘,如果输入负数返回-1
   * @param n 表示求 n 的阶乘
   * @return
   */
  public static int getFactorial(int n) {
      if (n >= 0) {
          if (n == 0) {
              System.out.println(n + " != 1");
              return 1;
          } else {
              System.out.println(n);
              int temp = n * getFactorial(n - 1);
              System.out.println(n + " != " + temp);
              return temp;
          }
      }
      return -1;
  }
  ```

- 二分查找
  ```java
  public static int search(int[] array,int key,int low,int high) {
      int mid = (high-low) / 2 + low;
      if (key == array[mid]) {
          // 查找值等于当前值，返回数组下标
          return mid;
      } else if (low > high) {
          // 找不到查找值，返回-1
          return -1;
      } else {
          if (key < array[mid]) {
              // 查找值比当前值小
              return search(array, key, low, mid-1);
          }
          if (key > array[mid]) {
              //查找值比当前值大
              return search(array, key, mid+1, high);
          }
      }
      return -1;
  }
  ```

- 汉诺塔问题
  ```java
  /*
   * 汉诺塔问题
   * @param dish 盘子个数(也表示名称)
   * @param from 初始塔座
   * @param temp 中介塔座
   * @param to   目标塔座
   */
  public static void move(int dish, String from, String temp, String to) {
      if (dish == 1) {
          System.out.print("将盘子" + dish);
          System.out.print("从塔座" + from);
          System.out.println( "移动到目标塔座" + to);
      } else {
          // A为初始塔座，B为目标塔座，C为中介塔座
          move(dish-1, from, to, temp);
          System.out.print("将盘子" + dish);
          System.out.print("从塔座" + from);
          System.out.println( "移动到目标塔座" + to);
          // B为初始塔座，C为目标塔座，A为中介塔座
          move(dish-1, temp, from, to);
      }
  }
  ```

- 归并排序
  ```java
  public static int[] mergeSort(int[] c,int start,int last) {
      if (last > start) {
          // 也可以是 (start+last)/2, 这样写是为了防止数组长度很大造成两者相加超过int范围，导致溢出
          int mid = start + (last - start)/2;
          mergeSort(c, start, mid);  // 左边数组排序
          mergeSort(c, mid+1, last);  // 右边数组排序
          merge(c, start, mid, last);  // 合并左右数组
      }
      return c;
  }
  ```

#### 消除递归
一个算法作为一个递归的方法通常通概念上很容易理解，但是递归的使用在方法的调用和返回都会有额外的开销，通常情况下，用递归能实现的，用循环都可以实现，而且循环的效率会更高，所以在实际应用中，把递归的算法转换为非递归的算法是非常有用的。这种转换通常会使用到栈。

#### 递归和栈
递归和栈有这紧密的联系，而且大多数编译器都是用栈来实现递归的，当调用一个方法时，编译器会把这个方法的所有参数和返回地址都压入栈中，然后把控制转移给这个方法。当这个方法返回时，这些值弹栈。参数消失了，并且控制权重新回到返回地址处。

调用一个方法时所发生的事：
1. 当一个方法被调用时，它的参数和返回地址被压入一个栈中；
1. 这个方法可以通过获取栈顶元素的值来访问它的参数；
1. 当这个方法要返回时，它查看栈以获得返回地址，然后这个地址以及方法的所有参数退栈，并且销毁。

### 树
树（`tree`）是一种抽象数据类型（`ADT`），用来模拟具有树状结构性质的数据集合。它是由 `n` (n > 0) 个有限节点通过连接它们的边组成一个具有层次关系的集合。把它叫做 “树” 是因为它看起来像一棵倒挂的树，也就是说它是根朝上，而叶朝下的。

#### 树的组成
- 节点
  - 节点一般代表一些实体。
  - 在 java 里，节点一般表示为对象。
- 边
  - 连接节点的线称为边，边表示节点的关联关系。
  - 一般从一个节点到另一个节点的唯一方法就是沿着一条顺着有边的道路前进。
  - 在 Java 当中通常表示为引用。
  
#### 树的常用术语
- 路径：
顺着节点的边从一个节点走到另一个节点，所经过的节点的顺序排列就称为 `路径` 。
- 根节点：树顶端的节点称为根。一棵树只有一个根，如果要把一个节点和边的集合称为树，那么从根到其他任何一个节点都必须有且只有一条路径。
- 父节点：若一个节点含有子节点，则这个节点称为其子节点的父节点。
- 子节点：一个节点含有的子树的根节点称为该节点的子节点。
- 兄弟节点：具有相同父节点的节点互称为兄弟节点。
- 叶节点：没有子节点的节点称为叶节点，也叫叶子节点。
- 子树：每个节点都可以作为子树的根，它和它所有的子节点、子节点的子节点等都包含在子树中。
- 节点的层次：从根开始定义，根为第一层，根的子节点为第二层，以此类推。
- 深度：对于任意节点 `n`, `n` 的深度为从根到 `n` 的唯一路径长。根的深度为 `0` 。
- 高度：对于任意节点 `n`，`n` 的高度为从 `n` 到一片树叶的最长路径长。所有树叶的高度为 `0`。

#### 二叉树
树的每个节点最多只能有两个子节点，并且二叉树的子节点称为 `左子节点` 和 `右子节点` ，也称为 `左孩子` 和 `右孩子` 。

#### 二叉搜索树
二叉搜索树要求：若它的左子树不空，则左子树上所有结点的值均小于它的根结点的值；若它的右子树不空，则右子树上所有结点的值均大于它的根结点的值；它的左、右子树也分别为二叉搜索树。

#### 哈夫曼树
哈夫曼树又叫最优二叉树，其通过某种规则（权值）来构造出一种特殊的二叉树，在这个二叉树中只有叶子节点才是有效的数据节点，其他的非叶子节点是为了构造出哈夫曼编码而引入的。

哈夫曼编码是一个通过哈夫曼树进行的一种编码，一般情况下，以字符：`0` 与 `1` 表示。编码的实现过程很简单：只要实现哈夫曼树，通过遍历哈夫曼树，规定向左子树遍历一个节点编码为 `0` ，向右遍历一个节点编码为 `1` ，结束条件就是遍历到叶子节点。这样就可以得到对应于叶子节点上数据的哈夫曼编码。

### 2-3-4 树
在二叉树中，每一个节点只有一个数据，最多两个子节点。如果允许每一个节点有更多的数据项和子节点，那么就产生了多叉树。

2-3-4 树就是一种多叉树，它的每一个节点最多有 `3` 个数据项和 `4` 个子节点。这种树的名字中 `2`, `3`, `4` 的数字含义是指一个节点可能含有的子节点的个数。它的非叶子节点有三种情况：

- 有 1 个数据项的节点总有 2 个子节点
- 有 2 个数据项的节点总有 3 个子节点
- 有 3 个数据项的节点总有 4 个子节点

简而言之，非叶节点的子节点数总是比它含有的数据项多1。也就是说如果子节点个数为 `L` ，数据项个数为 `D` ，那么：`L = D + 1`

叶子节点是没有子节点的，但是它却含有 1-3 个数据项。空节点是不存在的。

树结构中最重要的一点就是节点之间的数据项之间大小的关系。二叉树中，所有关键字比某一节点下的，都在这个节点的左子树上，否则，在这个节点的右子树上。2-3-4 树就是建立在在二叉树的基础上，其子树上所有的节点均处于根节点两个关键字之间。

如图所示：
![2-3-4 Tree](./picture/2-3-4_Tree.png)

#### 查找
在 2-3-4 树中查找特定关键字值的数据项和在二叉树中的搜索类似。从根节点开始搜索，除非查找的关键字值就是根，否则选择关键字值所在的合适范围，转向那个方向，直到找到为止。

#### 插入
新的数据项一般要插在叶节点里，而叶子节点都在树的最底层。如果插入到有子节点的节点里，那么子节点的编号就要发生变化来维持树的结构，因为在 2-3-4 树中节点的子节点要比数据项多 1。所以插入操作有时比较简单，有时却很复杂。
- 当插入没有满数据项的节点时是很简单的，找到合适的位置，只需要把新数据项插入就可以了，插入可能会涉及到在一个节点中移动一个或其他两个数据项，这样在新的数据项插入后关键字值仍保持正确的顺序。
- 如果往下寻找插入位置的途中，节点已经满了，那么插入就变得复杂了。发生这种情况时，节点必须分裂，分裂能保证 2-3-4树的平衡。

#### 节点分类
- 叶子节点分裂
  - 在要分裂的节点右边为之创建一个兄弟节点
  - 将数据项 `C` (最大/右数据) 移到新节点中
  - 数据项 `B` (中间数据) 移到要分裂节点的父节点中
  - 数据项 `A` (最小/左数据) 保留在原来的位置
  - 最右边的两个子节点从要分裂处断开，连到新节点上

分裂过程如下图所示：
![split1](./picture/split1.png)

如果一开始查找插入节点时就碰到满的根节点，那么插入过程更复杂：
- 根节点分裂
  - 为要分裂的根节点创建一个新的父节点
  - 再在该节点的右边为之创建一个兄弟节点
  - 数据项 `C` 移到新的兄弟节点中
  - 数据项 `B` 移到新的根节点中
  - 数据项 `A` 保留在原来的位置
  - 要分裂节点最右边的两个子节点断开连接，连到新的兄弟节点中

分裂过程如下图所示：
![split2](./picture/split2.png)

### 红黑树
二叉搜索树的左子树的节点关键值都小于该节点关键值，右子树的所有节点关键值都大于该节点关键值。所以，二叉搜索树的查找、插入和删除操作的时间复杂度都为 `O(log n)`。但是这个时间复杂度是在平衡的二叉搜索树上体现的。如果建树时插入的数据原本就是有序的，那么插入数据的时就会集中在树的一侧，这样就和链表没有区别了。所以，实际请况中，二叉搜索树的时间复杂度取决于书的平衡程度。

红黑树的就一种平衡树，对一个要插入（或者删除）的数据项，插入（或者删除）操作需要检查该操作会不会破坏树的平衡特征，如果树的平衡被破坏了，就需要根据情况调整树的结构（变色，左旋或者右旋），从而维持红黑树的平衡特征。

#### 红黑树的特征
红黑树主要具有两个特征：
- 树的每一个节点都是有颜色的
- 在插入（或者删除）操作过程中，要使这些颜色的排列满足一定的规则

红黑树颜色排列的规则：
1. 任何一个节点不是红色就必定是黑色
1. 根节点总时黑色的
1. 从每个叶子节点到根节点的所有路径上，不能有两个连续的红色节点
1. 从根节点到每个叶子节点或空子节点的每条路径，必须包含相同数目的黑色节点
> 注：新插入的节点颜色总是红色的，
这是因为插入一个红色节点比插入一个黑色节点违背红黑规则的可能性更小，
原因是插入黑色节点总会改变黑色高度（违背 `规则4`），
但是插入红色节点只有一半的机会会违背 `规则3`。

#### 红黑树的调整
红黑树主要通过三种方式对平衡特征进行调整：
- 变色
- 左旋
- 右旋

##### 变色
改变节点颜色，通常新插入的节点是红色，如果违背规则 3 就需要变色，变色之后检查是否违背 `规则4`。

变色操作如图：
![changeColor](./picture/changeColor.png)
> 注：变色也是为了更好地判断何时执行什么旋转，
而旋转是为了保证树的平衡。
仅仅变色是不能起到任何作用的，旋转才是关键的操作，
在新增节点或者删除节点之后，可能会破坏二叉树的平衡，
那么何时执行旋转以及执行什么旋转才是需要关注的重点。

##### 左旋
左旋主要分为三个步骤：
1. 将 `y` 的左子节点赋给 `x` 的右子节点，并将 `x `赋给 `y` 左子节点的父节点 ( `y` 左子节点非空时)
1. 将 `x` 的父节点 `p` (非空时)赋给 `y` 的父节点，同时更新 `p` 的子节点为 `y` (左或右)
1. 将 `y` 的左子节点设为 `x`，将 `x` 的父节点设为 `y`

如图所示：
![left](./picture/left.png)

##### 右旋
同左旋类似，右旋也是三步操作：
1. 将 `x` 的右子节点赋给y的左子节点，并将 `y` 赋给 `x` 右子节点的父节点 (`x`右子节点非空时)
1. 将 `y` 的父节点 `p` (非空时)赋给 `x` 的父节点，同时更新 `p` 的子节点为 `x`(左或右)
1. 将 `x` 的右子节点设为 `y`，将 `y` 的父节点设为 `x`

过程如图所示：
![right](./picture/right.png)

#### 红黑树插入
如果是第一次插入，由于原树为空，所以只会违反红黑树的规则2，所以只要把根节点涂黑即可；如果插入节点的父节点是黑色的，那不会违背红黑树的规则，什么也不需要做；但是遇到如下三种情况，就需要进行相应的调整：
1. 插入节点的父节点和父节点的兄弟节点（祖父节点的另一个子节点）均为红色
1. 插入节点的父节点是红色的，父节点的兄弟节点是黑色的，且插入节点是其父节点的右子节点
1. 插入节点的父节点是红色的，父节点的兄弟节点是黑色的，且插入节点是其父节点的左子节点

对于` 情况1`，此时一定存在祖父节点，由于对称性，讨论一侧的解决情况即可。此时要做的操作主要是：
- 将当前节点父节点以及其父节点的兄弟节点变为黑色，祖父节点变红，
- 再将当前节点指向其祖父节点，再次从新的当前节点开始算法。

此时变为 `情况2`。

对于 `情况2`，主要操作是：
- 将当前节点的父节点作为新的节点，以新的当前节点为支点进行左旋操作

完成后变为 `情况3`。

对于 `情况3`，主要操作是：
- 将当前节点的父节点涂黑，将祖父节点涂红，在祖父节点为支点做右旋操作
- 最后把根节点涂黑

此时，红黑树恢复平衡。

#### 红黑树的删除
红黑树的删除和二叉搜索树的删除是一样的，只不过删除后多了对树的平衡特征的修复步骤。

二叉树节点的删除：
- 如果待删除的节点没有子节点，那么直接删除即可
- 如果待删除的节点只有一个子节点，那么直接删掉，并用其子节点去顶替它。
- 如果待删除的节点有两个子节点，这种情况比较复杂：
  - 首先找出它的后继节点
  - 然后处理 `后继节点` 和 `被删除节点的父节点` 之间的关系
  - 最后处理 `后继节点的子节点` 和 `被删除节点的子节点` 之间的关系

实际上，删除过程比较，很多情况下会采用在节点类中添加一个删除标记，并不是真正的删除节点。

### 排序
在[递归部分](#%E9%80%92%E5%BD%92) 有关于归并排序的介绍，归并排序的时间复杂度是 `O(nlog n)`，速度很快，但是它使用的排序空间是原始数据所占空间的两倍，也就是说归并排序的空间复杂度很高。所以当存在空间限制的时候，是不能使用归并排序的。

#### 冒泡排序
冒泡排序的原理很简单，可以直观的理解为水里的气泡上浮。

具体步骤如下：
1. 比较相邻的两个元素，如果第一个比第二个大，就交换它们；
1. 对每一对相邻元素重复以上操作，这样，最后的元素会是最大的数（也就是第一波冒泡完成）；
1. 针对所有元素重复以上两步，直到没有任何一对数字需要比较

#### 选择排序
选择排序是每一次从待排序的数据元素中选出最小的一个元素，存放在序列的起始位置，直到全部待排序的数据元素排完。

步骤如下：
1. 从待排序序列中寻找最小的元素
1. 如果最小的元素不是第一个元素，则将其与第一个元素交换
1. 从余下的序列中继续重复以上步骤，直至选择完所有元素

#### 插入排序
直接插入排序基本思想是，每一次都将一个待排序的数据插入到前面已经排好序的有序数据序列中去，直到插完所有数据元素为止。

插入排序步骤如下：
1. 将需要插入的数据放在一个临时变量中，这也是一个标记符，标记符左边的数据是已经排好序的，标记符右边的数据是需要排序的。
1. 将标记的数据和左边排好序的数据进行比较，假如比目标数据大则将左边排好序的数据向右边移动一位，直到找到比其小的位置进行插入。

#### 希尔排序 
希尔排序是基于直接插入排序的，它为直接插入排序引入了一个新的特性，大大的提高了插入排序的执行效率。

希尔排序的诞生就是为了解决直接插入排序的效率问题的。希尔排序通过加大插入排序中数据元素的间隔，并在这些有间隔的数据元素中进行插入排序，
从而使数据元素能够大跨度的移动。当这些数据项排过一趟序后，
希尔排序算法减小数据元素之间的间隔再次进行排序，依次进行下去，最后间隔为 `1`。

通过以上描述，可以看出，排序间隔对于希尔排序是十分重要的。希尔的原稿中，他建议间隔选为 `N/2`，也就是每一趟都将排序分为两半。这个方法的好处是不需要在开始排序前为找到初始序列的间隔而计算序列，只需要用 `2` 整除 `N` 。但是这已经被证明并不是最好的序列。

间隔序列中的数字互质是很重要的指标，也就是说，除了 `1` 之外他们之间没有公约数。这个约束条件使得每一趟排序更有可能保持前一趟排序已经排好的结果，所以一种希尔的变形方法是用 `2.2` 来整除每一个间隔，这比用 `2` 整除会显著地改善排序效果。另外还有一种很常用的间隔序列：`knuth 间隔序列 3h+1`。但是无论是什么间隔序列，最后必须满足一个条件，就是逐渐减小的间隔最后一定要等于 `1`，因此最后一趟排序一定是简单的插入排序。

#### 快速排序
快速排序是对冒泡排序的一种改进，是 `C.A.R. Hoare` 在1962年提出的一种划分交换排序，采用的是分治策略（一般与递归结合使用），以减少排序过程中的比较次数。

快排地基本思路：
- 先通过第一趟排序，将数组原地划分为两部分，
其中一部分的所有数据都小于另一部分的所有数据。
- 通过递归的处理，再对原数组分割的两部分分别划分为两部分，同样是使得其中一部分的所有数据都小于另一部分的所有数据。
- 这样不断划分到最后，数组就被划分为多个由一个元素或多个相同元素组成的单元，
这样数组就有序了。

### 哈希表
哈希表 `Hash` 也称散列表，是一种可以根据根据关键字-值（key-value）直接进行访问的数据结构。

它基于数组，通过某种函数，把关键字映射到数组中的不同的下标来建立查找表，但是其又和数组、链表、树等数据结构不同，因为在这些数据结构中查找时，通常要遍历全部数据，时间复杂度为`O(N)`，但是对于哈希表来说，可以简化为`O(1)`。
> 注意，这里存在一个十分重要的问题：就是如何选择关键字转换函数。这个转换函数被称为哈希函数（也称散列函数），转换的过程被称为哈希化。

#### 哈希表引入
试想一下，如果我们想在内存中存取 50000 个单词，一个比较普遍的想法就是让每一个单词占据一个数组单元，同时使用数组下标存取单词，这是遇到一个问题就是该如何建立单词和数字之间的联系。

这时候有两种解决办法：
1. 使数组的每一个元素都包含一个子数组或者一个子链表，虽然这个办法在存储单词时表现良好，速度很快，但是查找效率并不优秀，查询数据很慢
1. 扩展数组的下标，使其能表示一个单词

扩展数组下标的方法也有很多，最常用的应该就是取模的方法
- 假设要把从 0-199 的数字（用`largeNumber`表示），压缩为 0-9 的数字（用`smallNumber`表示），因为后者有 10 个数，所以变量 `smallRange` 的值为10，这个转换的表达式为
`smallNumber = largeNumber % smallRange` 。 当一个数被 10 整除时，余数一定在 0-9 之间，这样，就很容易地把 0-199 的数压缩为 0-9 的数，压缩率为 `20:1`

#### 开放地址法
虽然压缩比很高了，但是面对这种压缩，肯定会存在不同的数被哈希化到同一个数字下标，这样就产生了冲突。冲突可能会导致哈希化方案无法实施。所以，当冲突产生时，就需要有一种方法来解决冲突，即找到一个新的位置存放冲突的数据，这就是开放地址法。开放地址法中，若数据项不能直接存放在由哈希函数所计算出来的数组下标对应的位置时，就要寻找其他的位置，主要有三种方法：线性探测法、二次探测法和再哈希法。

##### 线性探测法
使用线性探测法解决冲突时，遇到冲突的数据，它就会线性的查找空白单元。比如如果 `5421` 是要插入数据的位置，但是它已经被占用了，那么就使用 `5422`，如果 `5422` 也被占用了，那么使用 `5423`，以此类推，数组下标依次递增，直到找到空白的位置。这就叫做线性探测，因为它沿着数组下标一步步顺序的查找空白单元，来存放冲突数据。

**装填因子** 已填入哈希表的数据项和表长的比率叫做`装填因子`，比如有 10000 个单元的哈希表填入了 6667 个数据后，其装填因子为 2/3。当装填因子比较大时，每插入一个新的数据，都要频繁的探测插入位置，因为可能很多位置都被前面插入的数据所占用了，这称为聚集。线性探测法是一步一步的往后面探测，所以当装填因子比较大时，会频繁的产生聚集。这就比较耗时了。

##### 二次探测法
二测探测法是防止聚集产生的一种方式，其思想是探测相距较远的单元，而不是一步一步地探测。比如哈希函数计算的原始下标是`x`, 在二次探测中，探测的过程是`x+1`, `x+4`, `x+9`, `x+16` `...`，探测点到原始位置的距离是步数的平方。二次探测虽然消除了原始的聚集问题，但是产生了另一种更细的聚集问题，叫二次聚集：比如将 `184`, `302`, `420`和 `544` 依次插入表中，它们的映射都是 `7`，那么 `302` 需要以 `1` 为步长探测，`420` 需要以 `4` 为步长探测， `544` 需要以 `9` 为步长探测。只要有一项其关键字映射到 `7`，就需要更长步长的探测，这个现象叫做二次聚集。二次聚集不是一个严重的问题，但是二次探测不会经常使用，因为还有好的解决方法，比如再哈希法。

##### 再哈希法
再哈希法是为了消除原始聚集和二次聚集。其目的是产生一种依赖关键字的探测序列，而不是针对每个关键字都一样，那么，不同的关键字即使映射到相同的数组下标，也可以使用不同的探测序列。方法是把关键字用不同的哈希函数再一次哈希化，用这个结果作为探测步长。

这也对第二个哈希函数有一定的要求，其必须具备如下特点：
1. 和第一个哈希函数不同
2. 不能输出0（否则，将没有步长，每次探测都是原地踏步，算法将陷入死循环

专家们已经发现下面形式的哈希函数工作的非常好：`stepSize = constant - key % constant`。其中 `constant` 是质数且小于数组容量。再哈希法要求表的容量是一个质数，假如表长度为不是质数，比如 `15`，如果有一个特定关键字映射到 `0`，步长为 `5`，则探测序列是 `0, 5, 10, 0, 5, 10`,以此类推一直循环下去。算法只尝试这三个单元，所以不可能找到某些空白单元，最终算法导致崩溃。相反，如果数组容量是质数，如 `13`，探测序列最终会访问所有单元， 即 `0, 5, 10, 2, 7, 12, 4, 9, 1, 6, 11, 3`，一直下去，只要表中有一个空位，就可以探测到它。

#### 链地址法


### 堆

### 图
