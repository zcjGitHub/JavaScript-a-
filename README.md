# JavaScript-a++
执行a++到底发生了什么
在js中我们经常会用到'++'操作符。但是有时候还是会对这种解释器执行这段代码的机制不太清楚，下面将深入剖析执行'++'的背后的故事。首先我们看个例子：

```javascript
  var a = 0;
  var b = a++;//0
  console.log(a);//1
  a = a++;//1
```
看到这段代码如果对输出结果有疑惑的请继续看下面内容。

执行a++将会涉及到两个值，一个是表达式（a++）的值，还有一个是变量a的值。这两个值都先于给b赋值，并且变量的值的执行先于表达式的值的执行。因此，当执行var b = a++时；会将表达式(a++)的值赋给变量b，而（a++）的值是0,因此b = 0。当执行a = a++时，此时a的值是2，表达式（a++）的值是1，然后再执行赋值语句将（a++）的值赋给a,因此a的值变成1。