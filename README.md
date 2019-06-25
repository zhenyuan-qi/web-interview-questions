持续更新中...
# web-interview-question

一年之后再次回顾，会感谢曾经努力的自己！！

* 2019-06-25
 > apply、call和bind 的区别？
 
 都是改变函数运行时this的指向，先搞懂this
 
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

