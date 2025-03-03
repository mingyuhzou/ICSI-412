# Fundamentals

操作系统是用户和硬件的中介，二者紧密相连。

**1.可以使硬件更方便地被使用**

**2.管理系统资源，程序执行时所需的时间和空间，然而有的时候会出现冲突的目标，比如：最大化程序的吞吐量以及最小化响应时间**

**3.以一种更高效的方式使用硬件**

<img src="./assets/image-20250303210544456.png" alt="image-20250303210544456" style="zoom: 67%;" />

操作系统也可以表述为**用户应用程序和硬件之间的软件层**，**通过硬件接口抽象硬件，隐藏了运行时的大量细节**。

<img src="./assets/image-20250303210647613.png" alt="image-20250303210647613" style="zoom:67%;" />

基本的硬件资源有：

+ CPU：同一时间只有一个进程会在CPU上运行，一秒钟能运行数亿条指令，是最宝贵的资源，控制系统中所有的事物

+ Memory：容量有限，临时存储，是一种电子存储设备速度非常快，所有运行在CPU上的程序必须在内存中。

+ Storage(Disk)：容量大，用于储存，是一种机械装置，所有的数据以块为单位储存

+ I/O



系统类型：

+ Batch(批处理)：可以一次性提交大量的任务，系统决定运行那些
+ Time Sharing(分时)： 多个用户可以同时连接到同一台计算机，通过划分时间片在用户之间快速切换
+ Single User Interactive：传统的个人电脑
+ Parallel ：多处理器系统，通过多个处理器并行处理任务，提高**吞吐量（throughput）和容错能力（fault tolerance）**
+ Distributed(分布式)：多个联网计算机组成
+ Real-Time(实时系统)：对硬件和软件的**响应时间**有严格要求



单任务系统：同一时间只有一个程序运行，易于实现，利用率低 MS-DOS

多任务系统：较复杂，对系统资源的利用率更高，存在安全问题，Ubuntu, Windows 10









**操作系统一定保护自己免受用户影响**：例如操作系统会保留一部分内存区域(内核空间)为只有操作系统可以访问，防止用户程序修改或者破坏系统的核心部分。

**操作系统可能会保护用户彼此之间的安全**：即防止一个用户影响到另一个用户的数据或程序，但并非所有操作系统都实现。





**Dual-Mode Operation（双模式操作）** 是操作系统（OS）用于保护和安全的重要机制之一，它允许计算机区分 **用户模式（User Mode）** 和 **内核模式（Kernel/Supervisory Mode）**，以确保用户程序不会直接访问关键系统资源，从而保护操作系统的稳定性和安全性。



用户模式（User Mode）：**运行所有的用户应用程序，受限访问，只能执行基本的指令不能操作硬件( I/O 设备、内存管理)，如需访问受限资源需向操作系统请求服务(system call)**

内核模式（Kernel/Supervisory Mode）：**操作系统在该模式下运行，具有完全的权限**

**用户永远不要在内核模式下操作**