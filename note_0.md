###

1. := 方式用来指定初始化的时候带上右边表达式的初始化值

2. _ 运算符在import包路径的时候用来标记让包内的init函数在main函数执行前都执行；主要目的为了规避go语言中不允许引入包却不使用而报错的问题
   _ 在返回结果中使用如  _,error = readContent(file); 如果不关心某个值，可以用_进行忽略。

3. array 初始化需要指定长度，并且后续是不可以变化大小的。如 books = [3]string;
   也可以初始化指针类型数组，内部包含的是指针地址, 这种情况下如果复制数组，不会复制指针内代表的内容。
   books1 = [3]*string;
   books = [3]*string{0=new string(),1=new string(),2=new string()};
   books1 = books;
   这种情况下books1和books共享同一块内存；

4. slice 是以array基础实现的可变数据结构，通过append接口来实现动态添加内容，但是仍然不可以超过slice定义的最大容量
   