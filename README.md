# 25summer-prep-notes-CN
2025年春季暑期实习招聘准备笔记

**Java基础上中下**

（1）  
String str1 = "he";  
String str2 = "llo";  
String str3 = "world";  
String str4 = str1 + str2 + str3;  
// "+"拼接实际上是通过 StringBuilder 调用 append() 方法实现的，拼接完成之后调用 toString() 得到一个 String 对象  
// tips: 最好不要在循环内使用“+”进行String拼接。因为StringBuilder 对象是在循环内部被创建的，这意味着每循环一次就会创建一个 StringBuilder 对象  

（2）  
String sum = "a" + "b";  
// 编译期：常量折叠（Constant Folding）：编译器直接将 "a" + "b" 优化为 "ab"，所以不会在运行时进行字符串拼接  

（3）  
String sum = new String("a") + new String("b");  
// 运行时创建两个 new String("a") 和 new String("b")（堆上的对象，不进入字符串池）  
// 使用 StringBuilder 调用 append() 方法拼接  

（4）  
String a = new String("a") + "b";
// new String("a"):（运行时创建堆上对象）  
// "b":（字符串池中的字面量）  
// 使用 StringBuilder 调用 append() 方法拼接  
// 生成新字符串 "ab"（堆上新对象）  


**Java集合上下**


**源码分析**


