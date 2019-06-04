### 函数Call

使用call()方法，可以编写在不同对象上使用的方法

call() 方法是预定义的 JavaScript 方法。

通过 call()，您能够使用属于另一个对象的方法。
>
    var person={
        fullname:function(){

        }
    }

    var person1={
        firstname:
        lastname:
    }

    var person2={
        firstname:
        lastname:
    }

    person.fullName