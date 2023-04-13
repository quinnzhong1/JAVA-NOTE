# 泛型

## 常用泛型类

### ArrayList

* 有参数类型的泛型类
* 可添加或删减元素，不需要管数组容量，因为会自动调节
* ArrayList<T> - Type指定具体class类型
* 原理
  * 一开始的capacity没到之前，正常加入元素
  * 等到了capacity之后，新建一个更大的数组，把已有数组重新加进去
* 举例说明
```java
// 声明构造
ArrayList<String> e = new ArrayList<String>();
ArrayList<String> e1 = new ArrayList<>();
var e3 = new ArrayList<String>();
// add，最后返回true
e.add("aaa");
e.add("bbb");
// remove
e.remove("aaa");
//确认capacity时，可调用的方法，这样达到这个capacity之前，都不用新建数组并转移
e2.ensureCapacity(100);
Var e4 = new ArrayList<String>(100);
//查看实际含有的元素数量，永远不会大于capacity
e.size();
//当确认数组列表大小后，不再发生变化，可以使用trimToSize()
//把多余储存空间剪掉，只保留当前数量元素的储存空间
//set设置index,必须是arraylist里面已有的元素
e.set(3,"bbb");
//get by index
e.get(3);
```