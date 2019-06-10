### @property
>
    s=Student()
    s.score=999
*在绑定属性时直接将属性暴露，没办法检查参数*

>
    class Student(object):
        def get_score(self):
            retrun self.__score

        def set_score(self,value):
            if not isinstance(value,init):
                raise ValueError('score must be an integer')
            if value<0 or value>100:
                raise ValueError('score must between 0-100')
            self.__score=value

*现在可以进行参数的校验*

改进方法 使用**decorator**装饰器动态的加上功能 **@property**    
>
    class Student(object):

        @property
        #将一个getter方法变成属性
        def score(self):
            return self.__score

        @score.setter
        #负责把一个setter方法变成属性赋值 可控操作
        def score(self):
            if not isinstance(value, int):
            raise ValueError('score must be an integer!')
        if value < 0 or value > 100:
            raise ValueError('score must between 0 ~ 100!')
        self._score = value 


### 可读与只读方法
>
    class Student(object):

        @property
        def birth(self):
            return self.__birth

        @birth.setter
        def birth(self,value):
            self.__birth=value

        @property
        def age(self):
            return self.__age
*__age是只读属性，__birth是读写属性*            