# pthread

##
1、 建立线程的三个重要的函数，pthread_create,pthread_join,pthread_exit

    int pthread_create(pthread_t *thread,pthread_attr_t *attr,void*(*start_routine)(void*),void *arg)
    第一个参数标示一个线程,他是pthread_t类型的变量
    第二个参数标示设置线程的属性，如果为空，默认属性
    第三个参数标示线程运行的函数，就是线程进行的操作
    第四个参数标示线程函数运行时传入的参数。
    成功返回0
    
    int pthread_exit(void *retval)
    线程一旦创建好，内核可以调度内核线程来执行start_routine函数，并且执行完之后，确保安全，干净的退出，调养该函数。
    
    这个函数通过retval参数向线程的的回收者传递其退出信息。
    
    int pthread_join(pthread_t thread,void** retval)
    
    thread : 目标线程，retval:目标线程的返回的退出信息。
    主线程用于回收子线程的函数，类似于回收进程的wait和waitpid函数
    
    int pthread_cancel(pthread_t thread)
    
    用于取消一个线程
