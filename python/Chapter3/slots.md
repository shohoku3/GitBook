### 使用__slots__
*给一个实例绑定属性*
>
    class Student(Object):  
        pass
    s=Student()
    s.name='Micheal'#给实例动态的绑定属性

*给一个实例绑定方法*   
>
    def set_age(self,age):
        self.age=age
    from types import MethodType
    s.set_age=MethodType(set_age,s)
    s.set_age(25)

为了给所有的实例都绑定方法，可以给class绑定方法
def set_score(self,score):
    self.score=score

Student.set_score=set_score

### 使用__slots__
*允许在定义class时,定义一个特殊的__slots__变量 来限制该class实例添加的属性*

>
    class Student(object):
        __slots__=('name','age')#使用元组定义允许绑定的属性名称

    s=Student()
    s.name='Michael'
    s.age=25
    s.score=99 #default
*score不可以被绑定在实例上*
**__slots__定义的属性仅对当前类实例起作用，对继承的子类是不起作用的：**
