### collection 内置的集合模块
#### namedtuple 自定义元组
> 
    from collection import namedtuple
    Point=namedtuple('Point',['x','y'])
    p=Point(1,2)
*自定义元组 规定元组元素的个数 使用属性而不是索引访问元素*

*验证*
>
    isstance(p,Point)

####deque 双向表
使用*list*存储数据时 索引访问元素快 插入删除较慢 因为*list*是线性的存储
>
    from collection import deque
    q=deque(['a','b','c'])
    q.append('x')
    q.appendleft('y')

支持appendleft() popleft()

####defaultdict 返回默认的key
使用*dict*时，如果引用的key不存在，就会抛出*KeyError*
若希望有默认值返回*defaultdict*

>
    from collection import defaultdict
    dd=defaultdict(lambda:'N/A')

####OrderedDict 使得dict中的key有序
>
    from collection import OrderedDict
    d=dict([('a',1),('b',2),('c',3)])
    d
    -->返回的key是无序的
    od=OrderDict([('a',1),('c',3),('b',2)])
    -->返回key按照插入顺序排列
*OrderDict可以实现FIFO先进先出的dict*

#### chainmap
