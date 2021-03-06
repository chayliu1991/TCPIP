# 计算机网络出现的背景

计算机网络， 根据其规模可分为：

- WAN（Wide Area Network， 广域网），指覆盖多个远距离区域的远程网络
- MAN （Metropolitan Area Network，城域网），连接整个城市的网络
- LAN（Local Area Network， 局域网），一个楼层、 一栋楼或一个校园等相对较小的区域内的网络

LAN：

![](./img/lan.png)

WAN：

![](./img/wan.png)

# 计算机与网络发展的7个阶段  

## 批处理  

所谓批处理， 是指事先将用户程序和数据装入卡带或磁带， 并由计算机按照一定的顺序读取， 使用户所要执行的这些程序和数据能够一并批量得到处理的方式。  

![](./img/batch_processing.png)

## 分时系统  

分时系统（TSS，Time Sharing System ） 。 它是指多个终端（由键盘、 显示器等输入输出设备组成。 最初还包括打字机。 ） 与同一个计算机连接， 允许多个用户同时使用一台计算机的系统。  

![](./img/TSS.png)

## 计算机之间的通信  

计算机间的通信显著地提高了计算机的可用性。 人们不再局限于仅使用一台计算机进行处理， 而是逐渐使用多台计算机分布式处理， 最终一并得到返回结果。   

![](./img/pc_conncted.png)

## 计算机网络的产生  

80 年代一种能够互连多种计算机的网络随之诞生。 它能够让各式各样的计算机相互连接， 从大型的超级计算机或主机到小型的个人电脑。  

![](./img/pc_network.png)

## 互联网的普及  

无论相距多远， 世界各地的人们只要接入互联网， 就可以通过个人电脑实现即时沟通和交流。  

![](./img/access_to_internet.png)

## 以互联网技术为中心的时代  

能够联网的设备也不仅限于单纯的计算机， 而是扩展到了手机、 家用电器、 游戏机等许多其他产品。 或许在未来， 可能还会增加更多各式各样的现在无法想象的设备。  

![](./img/IP_network.png)

## 从“单纯建立连接”到“安全建立连接”  

在互联网普及的初期， 人们更关注单纯的连接性， 以不受任何限制地建立互联网连接为最终目的。 然而现在， 人们已不再满足于“单纯建立连接”， 而是更为追求“安全建立连接”的目标。  

# 协议  

协议就是计算机与计算机之间通过网络实现通信时事先达成的一种“约定”。 这种“约定”使那些由不同厂商的设备、 不同的CPU以及不同的操作系统组成的计算机之间， 只要遵循相同的协议就能够实现通信。 反之， 如果所使用的协议不同， 就无法实现通信。  

## 分组交换协议  

分组交换是指将大数据分割为一个个叫做包（Packet） 的较小单位进行传输的方法。 这里所说的包， 如同我们平常在邮局里见到的邮包。 分组交换就是将大数据分装为一个个这样的邮包交给对方。  

![](./img/packet_communication.png)

## 协议由谁规定  

ISO（International Organization for Standards， 国际标准化组织。 ） 制定了一个国际标准 OSI（Open Systems Interconnection， 开放式通信系统互联参考模型。 ） ， 对通信系统进行了标准化。 现在， OSI 所定义的协议虽然并没有得到普及， 但是在 OSI 协议设计之初作为其指导方针的 OSI 参考模型却常被用于网络协议的制定当中。  

TCP/IP 并非 ISO 所制定的某种国际标准。 而是由 IETF（Internet Engineering Task Force） 所建议的、 致力于推进其标准化作业的一种协议。  那些支持互联网的设备及软件， 也正着力遵循由 IETF 标准化的 TCP/IP 协议。  

# 协议分层与OSI参考模型  

议分层就如同计算机软件中的模块化开发。  

分层的优点：

- 分层可以将每个分层独立使用， 即使系统中某些分层发生变化， 也不会波及整个系统。 因此， 可以构造一个扩展性和灵活性都较强的系统
- 此外， 通过分层能够细分通信功能， 更易于单独实现每个分层的协议， 并界定各个分层的具体责任和义务

劣势：

- 可能就在于过分模块化、 使处理变得更加沉重以及每个模块都不得不实现相似的处理逻辑等问题

![](./img/protocol_layer.png)

## OSI参考模型  

OSI 参考模型将这样一个复杂的协议整理并分为了易于理解的 7 个分层：

![](./img/osi_layer.png)  

OSI 参考模型终究是一个“模型”， 它也只是对各层的作用做了一系列粗略的界定， 并没有对协议和接口进行详细的定义。 它对学习和设计协议只能起到一个引导的作用。  

## OSI 参考模型中各个分层的作用  

![](./img/roles_of_each_layer.png)

- 应用层：为应用程序提供服务并规定应用程序中通信相关的细节。 包括文件传输、 电子邮件、 远程登录（虚拟终端） 等协议
- 表示层：将应用处理的信息转换为适合网络传输的格式， 或将来自下一层的数据转换为上层能够处理的格式。 因此它主要负责数据格式的转换
- 会话层：负责建立和断开通信连接（数据流动的逻辑通路） ， 以及数据的分割等数据传输相关的管理
- 传输层：起着可靠传输的作用。 只在通信双方节点上进行处理， 而无需在路由器上处理
- 网络层：将数据传输到目标地址。 目标地址可以是多个网络通过路由器连接而成的某一个地址。 因此这一层主要负责寻址和路由选择
- 数据链路层：负责物理层面上互连的、 节点之间的通信传输。 例如，与 1 个以太网相连的 2 个节点之间的通信。将0、 1序列划分为具有意义的数据帧传送给对端（数据帧的生成与接收）
-  物理层：负责0、 1比特流（0、 1序列） 与电压的高低、 光的闪灭之间的互换  



# OSI参考模型通信处理举例  

## 7层通信  

![](./img/7_layer_communication.png)

- 发送方从第7层、 第6层到第1层由上至下按照顺序传输数据， 而接收端则从第1层、 第2层到第7层由下至上向每个上一级分层传输数据
- 每个分层上， 在处理由上一层传过来的数据时可以附上当前分层的协议所必须的“首部”信息。 然后接收端对收到的数据进行数据“首部”与“内容”的分离， 再转发给上一分层， 并最终将发送端的数据恢复为原状

## 会话层以上的处理  

假定用户A要给用户B发送一封内容为“早上好”邮件。  

![](./img/send_hello_email.png)

### 应用层  

从用户输入完所要发送的内容并点击“发送”按钮的那一刻开始， 就进入了应用层协议的处理。 该协议会在所要传送数据的前端附加一个首部（标签） 信息。 该首部标明了邮件内容为“早上好”和收件人为“B”。 这一附有首部信息的数据传送给主机B以后由该主机上的收发邮件软件通过“收信”功能获取内容。 主机B上的应用收到由主机A发送过来的数据后， 分析其数据首部与数据正文， 并将邮件保存到硬盘或是其他非易失性存储器。

![](./img/application_layer.png)

### 表示层  

利用表示层， 将数据从“某个计算机特定的数据格式”转换为“网络通用的标准数据格式”后再发送出去。 接收端主机收到数据以后将这些网络标准格式的数据恢复“该计算机特定的数据格式”， 然后再进行相应处理。

表示层与表示层之间为了识别编码格式也会附加首部信息， 从而将实际传输的数据转交给下一层去处理。  

![](./img/presentation_layer.png)

### 会话层  

决定采用何种连接方法是会话层的主要责任。

会话层也像应用层或表示层那样， 在其收到的数据前端附加首部或标签信息后再转发给下一层。 而这些首部或标签中记录着数据传送顺序的信息。  

![](./img/session_layer.png)



## 传输层以下的处理  

### 传输层  

进行建立连接或断开连接的处理（此处请注意， 会话层负责决定建立连接和断开连接的时机， 而传输层进行实际的建立和断开处理。 ），在两个主机之间创建逻辑上的通信连接即是传输层的主要作用。  

此外， 传输层为确保所传输的数据到达目标地址， 会在通信两端的计算机之间进行确认， 如果数据没有到达， 它会负责进行重发。  

保证数据传输的可靠性是传输层的一个重要作用。 为了确保可靠性， 在这一层也会为所要传输的数据附加首部以识别这一分层的数据。 然而， 实际上将数据传输给对端的处理是由网络层来完成的。  

![](./img/transport_layer.png)

### 网络层  

网络层的作用是在网络与网络相互连接的环境中， 将数据从发送端主机发送到接收端主机。  

![](./img/network_layer.png)

如图所示， 两端主机之间虽然有众多数据链路， 但能够将数据从主机A送到主机B也都是网络层的功劳。  

![](./img/network_layer2.png)

在实际发送数据时， 目的地址 至关重要。 这个地址是进行通信的网络中唯一指定的序号。   

### 数据链路层、 物理层  

通信传输实际上是通过物理的传输介质实现的。 数据链路层的作用就是在这些通过传输介质互连的设备之间进行数据处理。  

物理层中， 将数据的0、 1转换为电压和脉冲光传输给物理的传输介质， 而相互直连的设备之间使用地址实现传输。 这种地址被称为MAC（Media Access Control， 介质访问控制。 ） 地址， 也可称为物理地址或硬件地址。 采用MAC地址， 目的是为了识别连接到同一个传输介质上的设备。  

网络层与数据链路层都是基于目标地址将数据发送给接收端的， 但是网络层负责将整个数据发送给最终目标地址， 而数据链路层则只负责发送一个分段内的数据。  

![](./img/data_link_physical_layer.png)

# 传输方式的分类  

## 面向有连接型与面向无连接型  

通过网络发送数据， 大致可以分为面向有连接与面向无连接两种类型（面向无连接型包括以太网、 IP、UDP等协议。 面向有连接型包括ATM、 帧中继、 TCP等协议。 ） 。  

### 面向有连接类型

面向有连接型中， 在发送数据之前， 需要在收发主机之间连接一条通信线路。   

![](./img/connection.png)

### 面向无连接类型

面向无连接型则不要求建立和断开连接。 发送端可于任何时候自由发送数据，反之， 接收端也永远不知道自己会在何时从哪里收到数据。 因此， 在面向无连接的情况下， 接收端需要时常确认是否收到了数据。  

在面向无连接的通信中， 不需要确认对端是否存在。 即使接收端不存在或无法接收数据， 发送端也能将数据发送出去。  

![](./img/connectionless.png)

## 电路交换与分组交换  

目前， 网络通信方式大致分为两种——电路交换和分组交换。 电路交换技术的历史相对久远， 主要用于过去的电话网。 而分组交换技术则是一种较新的通信方式，  TCP/IP 正是采用了分组交换技术。  

在电路交换中， 交换机主要负责数据的中转处理。 计算机首先被连接到交换机上， 而交换机与交换机之间则由众多通信线路再继续连接。 因此计算机之间在发送数据时， 需要通过交换机与目标主机建立通信电路。 将连接电路称为建立连接。 建立好连接以后， 用户就可以一直使用这条电路， 直到该连接被断开为止。

如果某条电路只是用来连接两台计算机的通信线路， 就意味着只需在这两台计算机之间实现通信， 因此这两台计算机是可以独占线路进行数据传输的。 但是， 如果一条电路上连接了多台计算机， 而这些计算机之间需要相互传递数据， 就会出现新的问题。 鉴于一台计算机在收发信息时会独占整个电路， 其他计算机只能等待这台计算机处理结束以后才有机会使用这条电路收发数据。 并且在此过程中， 谁也无法预测某一台计算机的数据传输从何时开始又在何时结束。 如果并发用户数超过交换机之间的通信线路数， 就意味着通信根本无法实现。

为此， 人们想到了一个新的方法， 即让连接到通信电路的计算机将所要发送的数据分成多个数据包， 按照一定的顺序排列之后分别发送。 这就是分组交换。  有了分组交换， 数据被细分后， 所有的计算机就可以一齐收发数据， 这样也就提高了通信线路的利用率。 由于在分组的过程中， 已经在每个分组的首部写入了发送端和接收端的地址， 所以即使同一条线路同时为多个用户提供服务， 也可以明确区分每个分组数据发往的目的地， 以及它是与哪台计算机进行的通信。

![](./img/packet_switching.png)

分组交换的大致处理过程是： 发送端计算机将数据分组发送给路由器， 路由器收到这些分组数据以后， 缓存到自己的缓冲区， 然后再转发给目标计算机。因此， 分组交换也有另一个名称： 蓄积交换。  

在分组交换中， 计算机与路由器之间以及路由器与路由器之间通常只有一条通信线路。 因此， 这条线路其实是一条共享线路。 在电路交换中， 计算机之间的传输速度不变。 然而在分组交换中， 通信线路的速度可能会有所不同。 根据网络拥堵的情况， 数据达到目标地址的时间有长有短。 另外， 路由器的缓存饱和或溢出时， 甚至可能会发生分组数据丢失、 无法发送到对端的情况。  

![](./img/circuit_grouping_switch.png)

## 根据接收端数量分类  

![](./img/xcast.png)

### 单播（Unicast）  

指1对1通信。 早先的固定电话就是单播通信的一个典型例子。

### 广播（Broadcast）  

将消息从1台主机发送给与之相连的所有其他主机。 广播通信的一个典型例子就是电视播放， 它将电视信号一齐发送给非特定的多个接收对象。  

进行广播通信的计算机也有它们的广播范围。 只有在这个范围之内的计算机才能收到相应的广播消息。 这个范围叫做广播域。  

### 多播（Multicast）
多播与广播类似， 也是将消息发给多个接收主机。 不同之处在于多播要限定某一组主机作为接收端。 多播通信 最典型的例子就是电视会议， 这是由多组人在不同的地方参加的一种远程会议。   

### 任播（Anycast）
任播是指在特定的多台主机中选出一台作为接收端的一种通信方式。 虽然， 这种方式与多播有相似之处， 都是面向特定的一群主机， 但是它的行为却与多播不同。 任播通信从目标主机群中选择一台最符合网络条件的主机作为目标主机发送消息。 通常， 所被选中的那台特定主机将返回一个单播信号， 随后发送端主机会只跟这台主机进行通信。  

# 地址  

通信传输中， 发送端和接收端可以被视为通信主体。 它们都能由一个所谓“地址”的信息加以标识出来。  

## 地址的唯一性  

如果想让地址在通信当中发挥作用， 首先需要确定通信的主体。 一个地址必须明确地表示一个主体对象。 在同一个通信网络中不允许有两个相同地址的通信主体存在。 这也就是地址的唯一性。  

## 地址的层次性  

当地址总数并不是很多的情况下， 有了唯一地址就可以定位相互通信的主体。 然而， 当地址的总数越来越多时， 如何高效地从中找出通信的目标地址将成为一个重要的问题。 为此人们发现地址除了具有唯一性还需要具有层次性。   

![](./img/address_layer.png)

MAC 地址和 IP 地址在标识一个通信主体时虽然都具有唯一性， 但是它们当中只有 IP 地址具有层次性。  

MAC 地址由设备的制造厂商针对每块网卡（NIC（Network Interface Card） ， 也叫网卡进行分别指定。 人们可以通过制造商识别号、 制造商内部产品编号以及产品通用编号确保MAC地址的唯一性。 然而， 人们无法确定哪家厂商的哪个网卡被用到了哪个地方。虽然 MAC 地址是真正负责最终通信的地址， 但是在实际寻址过程中， IP 地址却必不可少。      

IP 地址由网络号和主机号两部分组成。 即使通信主体的 IP 地址不同， 若主机号不同， 网络号相同， 说明它们处于同一个网段。 通常， 同处一个网段的主机也都属于同一个部门或集团组织。 另一方面， 网络号相同的主机在组织结构、 提供商类型和地域分布上都比较集中， 也为 IP 寻址带来了极大的方便。这也是为什么说 IP 地址具有层次性的原因。   

网络传输中， 每个节点会根据分组数据的地址信息， 来判断该报文应该由哪个网卡发送出去。 为此， 各个地址会参考一个发出接口列表。 在这一点上 MAC 寻址与 IP 寻址是一样的。 只不过 MAC 寻址中所参考的这张表叫做地址转发表， 而 IP 寻址中所参考的叫做路由控制表。MAC 地址转发表中所记录的是实际的 MAC 地址本身，而路由表中记录的 IP 地址则是集中了之后的网络号（确切的说， 是网络号与子网掩码。）

![](./img/send_to_dst.png)

# 网络的构成要素  

搭建一套网络环境要涉及各种各样的电缆和网络设备。   

![](./img/network_elements.png)

![](./img/network_elements2.png)

![](./img/overview.png)

## 通信媒介与数据链路  

计算机网络是指计算机与计算机相连而组成的网络。计算机之间通过电缆相互连接。 电缆可以分为很多种， 包括双绞线电缆、 光纤电缆、 同轴电缆、 串行电缆等。   

![](./img/data_link.png)

### 传输速率与吞吐量  

在数据传输的过程中， 两个设备之间数据流动的物理速度称为传输速率。 单位为bps（Bits Per Second， 每秒比特数）：

- 各种传输媒介中信号的流动速度是恒定的。 因此， 即使数据链路的传输速率不相同， 也不会出现传输的速度忽快忽慢的情况
- 传输速率高也不是指单位数据流动的速度有多快， 而是指单位时间内传输的数据量有多少
- 传输速率又称作带宽（Bandwidth） 。 带宽越大网络传输能力就越强  

主机之间实际的传输速率被称作吞吐量。 其单位与带宽相同， 都是bps（Bits Per Second），吞吐量这个词不仅衡量带宽， 同时也衡量主机的CPU处理能力、 网络的拥堵程度、 报文中数据字段的占有份额（不含报文首部， 只计算数据字段本身） 等信息。  

### 网络设备之间的连接  

每个生产厂家都必须严格按照规格出产相应的网络设备， 否则会导致自身的产品无法与其他网络设备兼容， 或易出故障等问题。  

在实际搭建网络时， 不仅应该关注每款产品的规格参数， 还应该了解它们的兼容性， 并且更应该重视参考这些产品在实际长期使用过程当中所呈现的性能指标。

## 网卡  

任何一台计算机连接网络时， 必须要使用网卡（全称为网络接口卡） 。 网络接口卡（NIC（集成了连接局域网功能的设备。 有时会被集成到计算机的主板中， 有时也可以单独插入扩展槽使用。 Network Information Center的缩写也是NIC， 所以要注意区分。 ） ） 有时也被叫做网络适配器、 网卡、 LAN卡。  

没有配置NIC的计算机如果想接入以太网， 至少得外接一个扩展槽以便插入NIC。 无线局域网的情况下也是如此， 计算机必须具备能够接入无线网的NIC才能保证连接到网络。   

## 中继器  

中继器（Repeater） 是在OSI模型的第1层——物理层面上延长网络的设备。 由电缆传过来的电信号或光信号经由中继器的波形调整和放大再传给另一个电缆。  

![](./img/repeater.png)

一般情况下， 中继器的两端连接的是相同的通信媒介， 但有的中继器也可以完成不同媒介之间的转接工作。  

通过中继器而进行的网络延长， 其距离也并非可以无限扩大。 例如一个 10Mbps 的以太网最多可以用4个中继器分段连接， 而一个 100Mbps 的以太网则最多只能连两个中继器。  

有些中继器可以提供多个端口服务。 这种中继器被称作中继集线器或集线器。 因此， 集线器（中继集线器也可以简称为集线器或Hub ） 也可以看作是多口中继器， 每个端口都可以成为一个中继器。  

![](./img/hub.png)

## 网桥/2层交换机  

![](./img/bridge.png)

网桥是在OSI模型的第2层——数据链路层面上连接两个网络的设备。 它能够识别数据链路层中的数据帧 ， 并将这些数据帧临时存储于内存， 再重新生成信号作为一个全新的帧转发给相连的另一个网段。 由于能够存储这些数据帧， 网桥能够连接 10BASE-T 与 100BASE-TX 等传输速率完全不同的数据链路， 并且不限制连接网段的个数。   

数据链路的数据帧中有一个数据位叫做FCS（用CRC（Cyclic Redundancy Check， 循环冗余校验码） 方式校验数据帧中的位。 有时由于噪音导致通信传输当中数据信号越来越弱， 而这种CRC正是用来检查数据帧是否因此而受到破坏的。 ） ， 用以校验数据是否正确送达目的地。 网桥通过检查这个域中的值， 将那些损
坏的数据丢弃， 从而避免发送给其他的网段。此外， 网桥还能通过地址自学机制和过滤功能控制网络流量（网络上传输的数据报文的数量。 ） 。     

有些网桥能够判断是否将数据报文转发给相邻的网段， 这种网桥被称作自学式网桥。 这类网桥会记住曾经通过自己转发的所有数据帧的MAC地址， 并保存到自己里的内存表中。 由此， 可以判断哪个网段中包含持有哪类MAC地址的设备。  

![](./img/self_learning_bridge.png)

以太网等网络中经常使用的交换集线器（Hub（具有网桥功能的Hub叫做交换集线器。 只有中继器功能的Hub叫做集线器。 ） ） ， 现在基本也属于网桥的一种。 交换集线器中连接电缆的每个端口都能提供类似网桥的功能。  

![](./img/switching_hub.png)

## 路由器/3层交换机  

![](./img/router.png)

路由器是在 OSI 模型的第 3 层——网络层面上连接两个网络、 并对分组报文进行转发的设备。 网桥是根据物理地址（MAC地址） 进行处理， 而路由器/3层交换机则是根据 IP 地址进行处理的。 由此， TCP/IP 中网络层的地址就成为了 IP 地址。  

路由器可以连接不同的数据链路。 例如连接两个以太网， 或者连接一个以太网与一个FDDI。  

路由器还有分担网络负荷的作用 ， 甚至有些路由器具备一定的网络安全功能。 因此， 在连接网络与网络的设备当中。  

## 4～7层交换机  

![](./img/4_7_layer_switcher.png)

4～7层交换机负责处理OSI模型中从传输层至应用层的数据。 如果用TCP/IP分层模型来表述 4～7层交换机就是以TCP等协议的传输层及其上面的应用
层为基础， 分析收发数据， 并对其进行特定的处理。 

## 网关  

![](./img/gateway.png)

网关是OSI参考模型中负责将从传输层到应用层的数据进行转换和转发的设备。它与4～7层交换机一样都是处理传输层及以上的数据， 但是网关不仅转发数据还负责对数据进行转换， 它通常会使用一个表示层或应用层网关， 在两个不能进行直接通信的协议之间进行翻译， 最终实现两者之间的通信。  

在使用WWW（World Wide Web， 万维网） 时， 为了控制网络流量以及出于安全的考虑， 有时会使用代理服务器（Proxy Server） 。 这种代理服务器也是网关的一种， 称为应用网关。 有了代理服务器， 客户端与服务器之间无需在网络层上直接通信， 而是从传输层到应用层对数据和访问进行各种控制和处理。 防火墙就是一款通过网关通信， 针对不同应用提高安全性的产品。  

![](./img/proxy_server.png)

# 现代网络实态  

## 互联网通信  

![](./img/internet_service.png)

## 移动通信  

![](./img/mobile_communication.png)

手机一开机， 就会自动与距离最近的基站发生无线通信。 基站上设有特定手机基站天线， 基地本身也相当于网络的“接入层”。

由一部手机终端发送信号给另一个终端时， 它所发出的请求会一直传送到注册对端手机号码的基站， 如果对方接听了电话， 就等于在这两部手机之间建立了通信连接。

基站收集的通信请求被汇集到控制中心（“边缘网络”） ， 之后会再被接入到互连通信控制中心的主干网。 

## 从信息发布者的角度看网络  

![](./img/data_center.png)

数据中心由大型服务器、 存储以及计算机网络构成。 有些大型的数据中心甚至直接连接“主干网”。 即使是小规模的数据中心， 大多数情况下也会连接到“边缘网络”。

数据中心内部的网络中分布着3层交换机和高速路由器。 为了减少网络延迟， 也有人正在研究高性能2层交换机的使用。  





