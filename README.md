持续更新中...
# web-interview-question

一年之后再次回顾，会感谢曾经努力的自己！！

* _2019-06-25_
## apply、call和bind 的区别？
 
 都是改变函数运行时this的指向，可以借助它们实现继承，先搞懂this
 
 * 方法调用模式：
 ```
   var a = 1;
   var obj = {
       a:2,
       fn:function(){
          console.log(this.a);
       }
   }
   obj.fn() //2
```
 此时的this指向obj这个对象，obj.fn() ==> obj.fn.call(obj),
 事实上谁调用这个函数，this就指向谁。 
 > DOM对象绑定事件也属于方法调用模式，因此它绑定的this就是事件源DOM对象。例如：
 ````
 documnet.addEventListener("click",function(e){
    console.log(this);
    setTimeout(function(){
        console.log(this)
    },200);
 },false)
 // document  window 对象
 ````
 
 > call()第一个参数是要绑定给this的值，后面传入的是参数列表，当第一个参数为null
 、undefined 的时候，this默认指向window
 ```
   var arr = [1,34,54,13];
   var max = Math.max.call(null,arr[0],arr[1],arr[2],arr[3]) //54
    
```
 
 > apply()一个参数是要绑定给this的值，后面传入的是数组，当第一个参数为null
    、undefined 的时候，this默认指向window
 ```
 var arr=[1,45,123,23];
 var max = Math.max(null,arr) //123

```
 > bind 方法不会立即执行，返回的是一个改变了上下文 this 后的函数
 而原函数 this 并没有改变。
 
 
 ### tips
 
 在ES6的箭头函数下，call和apply将失效，对于箭头函数来说：
 * 箭头函数中this对象，就是定义时所在的对象，而不是使用时所在的对象；
 所以不需要 var self = this 这种写法
 
 * 箭头函数不可以当作构造函数，也就是说不可以使用new 命令，否则会抛出错误
 * 箭头函数不可以使用arguments对象，该对象在函数体内不存在 可以用 Rest 参数代替
 
 ````
//call 的实现

Function.prototype.myCall = function ``````````__``````````(){
    var self = arguments[0] || window;
    self.fn = this;//谁调用myCall方法，this就指向谁
    //由于使用call这个方法，参数个数不确定的  使用eval
    var args = [];
    for(var i=1;i<arguments.length.length;i++){
        args.push('arguments['+i+']');
    }
    var result = eval('self.fn('+args.join(',')+')');
    consoel.log(result)
    delete self.fn;
    return result;
}   

````
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

