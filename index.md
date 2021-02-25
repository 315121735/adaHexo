> java 调用C/C++ 底层jvm.dll文件创建虚拟机
>
> *类加载的过程*
>
> 加载 >> 验证 >> 准备 >> 解析 >> 初始化
>
> 栈(不同线程调用会在栈中开辟一个当前线程栈区域)
>
> > 栈帧(每个方法都会都会有一快对应的区域)
>
> GC调优,可以直接将方法区空间定义好，不需要进行扩容产生的full gc
>
> 堆
>
> > -Xms   -Xmx
>
> 栈
>
> > -Xss
>
> 新生代
>
> > -Xmn
>
> 方法区
>
> > -XX: MetaspaceSize 设置元空间初始空间大少，默认21M到达该值触发full gc，并进行自动调整,释放内存多就降低该值,释放空间少就不超过设置值就提高该值
> >
> > -XX:MaxMetaspaceSize 设置元空间最大值,默认是-1，既不限制，根据本地内存大少
>
> -XX:-UseCompressedOops 禁止指针压缩 jdk1.8默认开启
>
> -XX:+UseCompressedClassPointers jdk1.8默认开启只压缩对象头里的Klass pointer
>
> -XX:-DoEscapeAnalysis 关闭逃逸分析(用来优化内存分配位置) jdk8默认开启
>
> -XX:+PrintGC 开启GC日志打印
>
> -XX:+PrintGCDetails 打印JVM参数
>
> -XX:MaxTenuringThreshold 设置进入老年代年龄

