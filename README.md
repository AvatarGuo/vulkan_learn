
# 0 ：（暂撇开环境）
## a. 智能指针和RAII原则

内存 对象创建：RAII原则，突然又看到了智能指针，发现很多技术都是相通的。

c++端的 :RAII资源说明 https://docs.microsoft.com/zh-cn/cpp/cpp/object-lifetime-and-resource-management-modern-cpp?view=msvc-170 

wiki： https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization
又顺带关联出了智能指针。即数据驱动，函数因为在栈上被调用，当函数返回时，程序内部会进行清理，如果new的话 会在堆上申请一块存储空间，（c#托管堆内存，单独跑了个程序在清理堆内存，c++没有GC一个弱化版的模版类，即智能指针）

vukan的对象初始化
https://docs.microsoft.com/zh-cn/cpp/cpp/smart-pointers-modern-cpp?view=msvc-170

智能指针（弱化版GC，模板类）比较好的一个说明：https://docs.microsoft.com/zh-cn/cpp/cpp/smart-pointers-modern-cpp?view=msvc-170

    unique_ptr：只允许基础指针的一个所有者
    shared_ptr：采用引用计数的智能指针 
    weak_ptr： 不计算引用计数的指针
如104:std::shared_ptr<Surface> m_surface; （模板类 ，类似省了析构函数主动destroy）
