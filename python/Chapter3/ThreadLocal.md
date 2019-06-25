### ThreadLocal
**解决**解决了线程局部变量访问问题
>
    import threading
    #创建全局ThreadLocal对象
    local_school=threading.local()
    def process_student():
        std=local_school.student
        print('Hello,%s(in %s)' %(std,threading.current_thread().name))

    def process_thread(name):
        local_school.student=name
        process_student()

    t1=threading.Thread(target=process_thread,args=('Alice',),name='Thread-A')
    t1=threading.Thread(target=process_thread,args=('Alice',),name='Thread-A')
    t1.start()
    t2.start()