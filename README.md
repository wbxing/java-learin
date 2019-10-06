# DataStructure

## Java 的一些数据结构

### 数据结构

  数据结构是计算机存储、组织数据的方式，
  指相互之间存在一种或多种特定关系的数据元素的集合。
  通常情况下，精心选择的数据结构可以带来更高的运行或者存储效率。
  数据结构往往同高效的检索算法和索引技术有关。

#### 数据结构的基本功能
  
  - 添加某一数据项
  - 删除某一特定数据项
  - 查找某一特定数据项
  - 迭代访问各个数据项
  
#### 常用数据结构

  - 数组 Array
  - 链表 Linked List
  - 栈 Stack
  - 队列 Queue
  - 树 Tree
  - 哈希表 Hash Table
  - 堆 Heap
  - 图 Graph
  
### 数组

#### 数组的声明

  - 第一种方式：
  
    > 数据类型 []  数组名称 = new 数据类型[数组长度];
  
    这里 [] 可以放在数组名称的前面，
    也可以放在数组名称的后面，
    我们推荐放在数组名称的前面，
    这样看上去 数据类型 [] 表示的很明显是一个数组类型，
    而放在数组名称后面，则不是那么直观。  
  
  - 第二种方式
  
    > 数据类型 [] 数组名称 = {数组元素1，数组元素2，......};
    
    这种方式声明数组的同时直接给定了数组的元素，
    数组的大小由给定的数组元素个数决定。
               
   ```java
   // 声明数组1,声明一个长度为3，只能存放int类型的数据
   int [] myArray = new int[3];
   // 声明数组2,声明一个数组元素为 1,2,3的int类型数组
   int [] myArray2 = {1,2,3};
   ``` 
    
#### 访问数组元素以及给数组元素赋值
      
  数组是存在下标索引的，
  通过下标可以获取指定位置的元素，
  数组下标是从0开始的，
  也就是说下标0对应的就是数组中第1个元素，
  可以很方便的对数组中的元素进行存取操作。
    
  前面数组的声明第二种方式，
  我们在声明数组的同时，
  也进行了初始化赋值。

   ```java
   // 声明数组,声明一个长度为3，只能存放int类型的数据
   int [] myArray = new int[3];
   // 给myArray第一个元素赋值1
   myArray[0] = 1;
   // 访问myArray的第一个元素
   System.out.println(myArray[0]);
   ```

#### 数组遍历
   
  数组有个 length 属性，
  是记录数组的长度的，
  我们可以利用length属性来遍历数组。
  
```java
// 声明数组2,声明一个数组元素为 1,2,3的int类型数组
int [] myArray2 = {1,2,3};
for(int i = 0 ; i < myArray2.length ; i++){
    System.out.println(myArray2[i]);
}
```
