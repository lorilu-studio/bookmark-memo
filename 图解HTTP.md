# 图解HTTP
# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#af291936)一、了解Web与网络基础
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#efb0c357)1、我们在网页浏览器（Web browser）的地址栏中输入 URL时，Web 页面是如何呈现的吗？
 ![](https://cdn.nlark.com/yuque/0/2019/png/111898/1550566749110-552cc739-caf2-4681-8fa0-164d4c55c2c3.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#ccb5debb)2、Http的版本历史
1)、HTTP/0.9

HTTP 于 1990 年问世。那时的 HTTP 并没有作为正式的标准被建立。

2)、HTTP/1.0

HTTP 在 1996 年的 5 月被公布，版本被命名为HTTP/1.0，并记载于 RFC1945。

3)、HTTP/1.1

1997 年 1 月公布的 HTTP/1.1 是目前主流的 HTTP 协议版本 发布修订版 RFC2616

## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#c36ef913)3、TCP/IP和HTTP的关系是什么？TCP/IP是什么，包括哪些？
+ 使用的网络（包括互联网）是在TCP/IP 协议族的基础上运作的。而HTTP 属于它内部的一个子集。
+ 不同的硬件、操作系统之间的通信所需要的规则称之为协议，而把互联网相关联的协议的集合称之为TCP/IP



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#138fa77d)4、TCP/IP的分层有哪些，主要的作用？
 应用层、传输层、网络层、数据链路层

+ 应用层

应用层决定了向用户提供应用服务时通信的活动。主要包括：TCP/IP 协议族内预存了各类通用的应用服务。比如，FTP（File

Transfer Protocol，文件传输协议）和 DNS（Domain Name System，域名系统）服务就是其中两类。HTTP 协议也处于该层。

+ 传输层：

提供处于网络连接中的两台计算机之间的数据传输。主要包括：TCP（Transmission Control Protocol，传输控制协议）和 UDP（User Data Protocol，用户数据报协议）。

+ 网络层（又名网络互连层）

用来处理在网络上流动的数据包。数据包是网络传输的最小数据单位。

+ 链路层（又名数据链路层，网络接口层）

处理连接网络的硬件部分。包括控制操作系统、硬件的设备驱动、NIC（Network Interface Card，网络适配器，即网卡），及光纤等物理可见部分（还包括连接器等一切传输媒介）。硬件上的范畴均在链路层的作用范围之内。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#a520cdbb)5、TCP/IP 通信传输流过程
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318043291-124cbdf0-640b-42c4-8e9c-0107721704d8.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#27b44aba)6、IP就是IP地址么？
答案：IP不等于IP地址，IP (Internet Protocol) 是网际协议，位于网络层。TCP/IP中的IP指的就是网际协议。IP协议的作用是把各种数据包传送给对方。而确保传送到对方需要满足各类条件。最重要的就是IP地址和MAC地址。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#426e7843)7、IP间的通信方式？
IP的通信是依赖MAC地址的。IP通过协议ARP协议（地址解析协议）将通信方的IP地址反查出对应的MAC地址



![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318076915-9b3eeacf-20de-45fd-be73-e4dba9aea6e3.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#5bcc5028)8、TCP协议的作用
TCP位于传输层，提供可靠的字节流服务。简单来说：TCP 协议为了更容易传送大数据才把数据分割，而且TCP 协议能够确认数据最终是否送达到对方。期间采用了三次握手策略：。握手过程中使用了TCP 的标志（flag）——SYN（synchronize）和ACK（acknowledgement）。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318095405-a54680b2-d436-4d21-bb7b-1aa83db1b709.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#3ac19912)9、DNS协议的作用
DNS（Domain Name System）服务是和HTTP 协议一样位于应用层的协议。它提供域名到IP 地址之间的解析服务。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318116262-d1ea4ed7-c690-4aef-9c89-3ebdb4d46693.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#68b86463)10、各种协议与HTTP的关系是什么？
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318132911-1649c2cf-0981-470c-ac78-70de44c74e07.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#64a956db)11、URI与URL的区别
URI --- 统一资源标识符 （Uniform Resource Identifier）

URI 用字符串标识某一互联网资源

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318165938-b334f00a-7e29-4b32-af1d-ee614d0cda60.png)

URL--- 统一资源定位符 （Uniform Resource Locator）

URL 表示资源的地点（互联网上所处的位置）。所以URL 是URI 的子集。

# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#871a8575)二、简单的HTTP协议
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#3f6f858c)1、HTTP协议的作用？
答：用于客户端（请求访问文本或图像等资源的一端）和服务器（提供资源响应的一端）之间的通信。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#55abe5bb)2、HTTP的特性有哪些？
答：1) 请求必定由客户端发出，而服务器端回复响应

         2)  HTTP协议对于发送过的请求或响应都不做持久化处理，即HTTP 是一种不保存状态，即无状态（stateless）协议

       3）HTTP 协议使用URI 定位互联网上的资源



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#69e4d95b)3、HTTP是如何进行连接通信的？
第一阶段：进行一次HTTP 通信就要断开一次 TCP 连接。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318204224-304aea7b-0d77-4156-b9f4-9098d653ef52.png)

第二阶段：采用持久连接（HTTP Persistent Connections，也称为HTTP keep-alive 或

HTTP connection reuse）的方法。持久连接的特点是，只要任意一端没有明确提出断开连接，则保持TCP连接状态。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318214091-ea371681-c382-4e69-afb6-6ad63153d997.png)

第三阶段：采用管线化技术，不用等待响应亦可直接发送下一个请求。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318225721-561fc765-8ced-4937-a041-c406ce6f8b63.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#b3094308)4、Cookie是怎么出现的？
答：为了保留HTTP无状态协议这个特征的同时又要解决HTTP协议无法根据之前的状态进行本次的请求处理的问题，于是引入了Cookie 技术。Cookie 技术通过在请求和响应报文中写入Cookie 信息来控制客户端的状态。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#5b418ec1)5、Cookies信息请求过程
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318247397-45f8fae3-67d8-4a5c-9ac5-3e2d42fa215e.png)



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#d9d589c3)三、HTTP报文内的HTTP信息
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#df5cf09b)1、HTTP报文是什么？
答：用于HTTP 协议交互的信息被称为HTTP 报文

HTTP报文分为报文首部和报文主体两块。两者由最初出现的空行（CR+LF）来划分。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318275110-b9a6e428-d190-434a-b478-055be44b2139.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318280589-e3566d47-23a7-495e-bd79-17aa3e4db5cc.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#93185082)2、常用的内容编码有哪几种？
gzip (GUN zip)  compress(UNIX 系统标准压缩)  deflate (zlib)  identity ( 不进行编码 )



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#597b3ea7)四、返回结果的HTTP状态码
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#8b8844a4)1、HTTP的状态码是什么？
状态码的职责是当客户端向服务器端发送请求时，描述返回的请求结果。借助状态码，用户可以知道服务器端是正常处理了请求，还是出现了错误。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#42a6afbb)2、状态码的类别
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318315153-741de9ad-908d-4d0b-810b-7e0b5e92e682.png)

## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#cee76344)3、2XX成功 (请求被正常处理)
+ 200 OK

表示从客户端发来的请求在服务器端被正常处理了。



+ 204 No Content 

表示服务器接收的请求已成功处理，但在返回的响应报文中不含实体的主体部分。另外，也不允许返回任何实体的主体。



+  206 Partial Content

表示客户端进行了范围请求，而服务器成功执行了这部分的GET 请求。响应报文中包含由Content-Range 指定范围的实体内容。

## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#1be36b3a)4、3XX重定向 (浏览器需要执行某些特殊的处理以正确处理请求)
+ 301 Moved Permanently 

永久性重定向，表示请求的资源已被分配了新的URI，以后应使用资源现在所指的URI。



+ 302 Found

临时性重定向。该状态码表示请求的资源已被分配了新的URI，希望用户（本次）能使用新的URI 访问。



+ 303 See Other

由于请求对应的资源存在着另一个URI，应使用GET方法定向获取请求的资源。(注：303 状态码和302 Found 状态码有着相同的功能，但303 状态码明确表示客户端应当采用GET 方法获取资源，这点与302 状态码有区别.)



+ 304 Not Modified

表示客户端发送附带条件的请求时，服务器端允许请求访问资源，但未满足条件的情况。304 状态码返回时，不包含任何响应的主体部分。304 虽然被划分在3XX 类别中，但是和重定向没有关系。(注：附带条件的请求是指采用GET 方法的请求报文中包含If-Match，If-Modified-Since，If-None-Match，If-Range，If-Unmodified-Since中任一首部。)



+ 307 Temporary Redirect

 临时重定向。该状态码与302 Found 有着相同的含义。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#129cf680)5、4XX客户端错误 (表明客户端是发生错误的原因所在)
+ 400 Bad Request

表示请求报文中存在语法错误。当错误发生时，需修改请求的内容后再次发送请求

+ 401 Unauthorized

表示发送的请求需要有通过HTTP 认证（BASIC 认证、DIGEST 认证）的认证信息。另外若之前已进行过1 次请求，则表示用户认证失败。

+ 403 Forbidden

表明对请求资源的访问被服务器拒绝了。（未获得文件系统的访问授权，问权限出现某些问题（从未授权的发送源IP 地址试图访问）等列举的情况都可能是发生403 的原因。）

+ 404 Not Found

 表明服务器上无法找到请求的资源。除此之外，也可以在服务器端拒绝请求且不想说明理由时使用。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#690ab62d)6、5XX服务器错误（表明服务器本身发生错误。）
+ 500 Internal Server Error 

表明服务器端在执行请求时发生了错误。也有可能是Web应用存在的bug 或某些临时的故障。

+ 503 Service Unavailable 

表明服务器暂时处于超负载或正在进行停机维护，现在无法处理请求。



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#6c47c307)五、与HTTP协作的Web服务器
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#8bc0f857)1、如何用单台虚拟主机实现多个域名?
**原理**：HTTP/1.1 规范允许一台HTTP 服务器搭建多个Web 站点。比如，提供Web 托管服务（Web Hosting Service）的供应商，可以用一台服务器为多位客户服务，也可以以每位客户持有的域名运行各自不同的网站。这是因为利用了虚拟主机（Virtual Host，又称虚拟服务器）的功能。

**实际情况**：如果一台服务器内托管了www.tricorder.jp 和www.hackr.jp这两个域名，当收到请求时就需要弄清楚究竟要访问哪个域名。在相同的IP 地址下，由于虚拟主机可以寄存多个不同主机名和域名的Web 网站，因此在发送HTTP 请求时，必须在Host 首部内完整指定主机名或域名的URI。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#4cf4db00)2、通信数据转发程序：代理、网关、隧道
代理：代理服务器的基本行为就是接收客户端发送的请求后转发给其他服务器。代理不改变请求URI，会直接发送给前方持有资源的目标服务器。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318652138-412196c8-b4b1-458c-afc2-38ad89bdb39b.png)

代理有多种使用方法，按两种基准分类。一种是是否使用缓存，另一种是是否会修改报文。

+ 缓存代理

代理转发响应时，缓存代理（Caching Proxy）会预先将资源的副本（缓存）保存在代理服务器上。当代理再次接收到对相同资源的请求时，就可以不从源服务器那里获取资源，而是将之前缓存的资源作为响应返回。

+ 透明代理

转发请求或响应时，不对报文做任何加工的代理类型被称为透明代理（Transparent Proxy）。反之，对报文内容进行加工的代理被称为非透明代理。

 

网关：网关的工作机制和代理十分相似。而网关能使通信线路上的服务器提供非HTTP 协议服务。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318681462-bd00bfb1-9408-49e8-97dd-155abc5a247d.png)





隧道：隧道可按要求建立起一条与其他服务器的通信线路，届时使用SSL等加密手段进行通信。隧道的目的是确保客户端能与服务器进行安全的通信。隧道本身不会去解析HTTP 请求。也就是说，请求保持原样中转给之后的服务器。隧道会在通信双方断开连接时结束。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318696358-5ca9495a-38a4-439e-aae2-e4706da36872.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#fce6d24c)3、在HTTP 出现之前的协议有哪些?
**FTP****（**** File Transfer Protocol****）**

传输文件时使用的协议。该协议历史久远，可追溯到1973 年前后，比TCP/IP 协议族的出现还要早。虽然它在1995 年被HTTP 的流量（Traffic）超越，但时至今日，仍被广泛沿用。

 

**NNTP****（**** Network News Transfer Protocol****）**

用于NetNews 电子会议室内传送消息的协议。在1986 年前后出现，属于比较古老的一类协议。现在，利用Web 交换信息已成主流，所以该协议已经不怎么使用了。

**Archie**

搜索anonymous FTP 公开的文件信息的协议。1990 年前后出现，现在已经不常使用。

 

**WAIS****（****Wide Area Information Servers****）**

以关键词检索多个数据库使用的协议。1991 年前后出现。由于现在已经被HTTP 协议替代，也已经不怎么使用了。

 

**Gopher**

查找与互联网连接的计算机内信息的协议。1991 年前后出现，由于现在已经被HTTP 协议替代，也已经不怎么使用了。



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#be9909ec)六、HTTP首部
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#edf33af4)1、HTTP 首部字段重复了会如何？
当HTTP 报文首部中出现了两个或两个以上具有相同首部字段名时会怎么样？

这种情况在规范内尚未明确，根据浏览器内部处理逻辑的不同，结果可能并不一致。有些浏览器会优先处理第一次出现的首部字段，而有些则会优先处理最后出现的首部字段。

## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#93f0d263)2、4种HTTP 首部字段类型介绍
+ 通用首部字段（General Header Fields）

<font style="color:black;">请求报文和响应报文两方都会使用的首部。</font>

+ 请求首部字段（Request Header Fields）

从客户端向服务器端发送请求报文时使用的首部。补充了请求的附加内容、客户端信息、响应内容相关优先级等信息。

+ 响应首部字段（Response Header Fields）

从服务器端向客户端返回响应报文时使用的首部。补充了响应的附加内容，也会要求客户端附加额外的内容信息。

+ 实体首部字段（Entity Header Fields）

针对请求报文和响应报文的实体部分使用的首部。补充了资源内容更新时间等与实体有关的信息。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#7e6d32dd)3、HTTP/1.1 首部字段概览表
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318804232-b46da1dc-96b9-4a7b-b3f3-e0a9dd509dc3.png)

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318809456-e5d80eee-ee99-4bb8-acee-0b7874914eb0.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318817770-d0ce8ab1-cfef-429f-98fe-131a2912861d.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548318822756-0e18515c-d310-4004-870d-911a0f78bc6f.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#6d61c348)4、End-to-end首部和Hop-by-hop首部
HTTP首部字段将定义成缓存代理和非缓存代理的行为，分为**端到端首部(End-to-end Header)**和**逐条首部(Hop-by-hop Header)**

下面列举了HTTP/1.1中的逐条首部字段，除这8种首部字段外，其他所有字段都属于端到端首部。

+ **Connection**
+ **Keep-Alive**
+ **Proxy-Authenticate**
+ **Proxy-Authorization**
+ **Trailer**
+ **TE**
+ **Transfer-Encoding**
+ **Upgrade**



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#b661af3e)5、HTTP/1.1通用首部字段
请求报文和响应报文双方都会使用的首部

+ **Cache-Control**

     操作缓存的工作机制，指令的参数是可选的，多个指令之间通过“,”分隔。首部字段

Cache-Control 的指令可用于请求及响应时。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548830869845-ed1adeba-64ad-44af-a4cb-7c970a3dd0a9.png)



_**Cache-Control指令一览**_

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831369428-cfe91b21-a275-4199-baa4-ffaa957ed211.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831390040-4c773521-43f1-45f6-9dd0-7032494fdc84.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831408998-fb872d41-c9b5-414e-a1c4-ba43670ba587.png)



+ **Connection**

1、控制不再转发给代理的首部字段

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831507414-e40e3b1e-e58f-40e4-ad06-b0e72369954a.png)

2、管理持久连接

     ![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831548833-517cc061-8c4b-4621-b543-33d2baa53463.png)

HTTP/1.1 版本的默认连接都是持久连接。为此，客户端会在持久连接上连续发送请求。当服务器端想明确断开连接时， 则指定Connection 首部字段的值为Close。



+ **Date**

Date 表明创建HTTP 报文的日期和时间。



+ **Progma**

该首部字段属于通用首部字段，但只用在客户端发送的请求中。客户端会要求所有的中间服务器不返回缓存的资源。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831896554-d76928f4-324d-4271-852e-356b0378f193.png)



+ **Trailer**

首部字段Trailer 会事先说明在报文主体后记录了哪些首部字段。该首部字段可应用在HTTP/1.1 版本分块传输编码时。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548831957963-e82132ab-de52-4992-94fc-5d23b92c9023.png)



+ **Transfer-Encoding**

首部字段Transfer-Encoding 规定了传输报文主体时采用的编码方式。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832005555-11cf1629-cb87-4d13-9f52-714a1dbe3ad4.png)



+ **Upgrade**

首部字段Upgrade 用于检测HTTP 协议及其他协议是否可使用更高的版本进行通信，其参数值可以用来指定一个完全不同的通信协议。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832055826-34e2f123-396d-4a70-b075-277ae2b268dd.png)



+ **Via**

首部字段Via 是为了追踪客户端与服务器之间的请求和响应报文的传输路径。

报文经过代理或网关时，会先在首部字段Via 中附加该服务器的信息，然后再进行转发。这个做法和traceroute 及电子邮件的Received 首部的工作机制很类似。

首部字段Via 不仅用于追踪报文的转发，还可避免请求回环的发生。所以必须在经过代理时附加该首部字段内容。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832152676-6645fe4a-56f7-4633-938d-d50f1ae12007.png)



+ **Warning**

Warning 首部是从HTTP/1.0 的响应首部（Retry-After）演变过来的。该首部通常会告知用户一些与缓存相关的问题的警告。Warning 首部的格式如下。最后的日期时间部分可省略。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832213667-9e024759-be2c-488f-ba2e-eb9970dfa074.png)

HTTP/1.1 中定义了7 种警告。警告码对应的警告内容仅推荐参考。另外，警告码具备扩展性，今后有可能追加新的警告码。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832252433-f626a3c3-4651-41ec-a984-ad2235622b65.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832270880-6a60ece5-8450-47c9-a223-7fad8a0de2fd.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#0653218d)6、请求首部字段
+ **Accept**

Accept 首部字段可通知服务器，用户代理能够处理的媒体类型及媒体类型的相对优先级。 可使用type/subtype 这种形式，一次指定多种媒体类型。

试举几个媒体类型的例子。

●●文本文件

text/html, text/plain, text/css ...

application/xhtml+xml, application/xml ...

●●图片文件

image/jpeg, image/gif, image/png ...

●●视频文件

video/mpeg, video/quicktime ...

●●应用程序使用的二进制文件

application/octet-stream, application/zip ...



+ **Accept-Charset**

Accept-Charset 首部字段可用来通知服务器用户代理支持的字符集及字符集的相对优先顺序。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548832943916-0f12aa00-6740-4957-9b53-aef927275a04.png)



+ **Accept-Encoding**

Accept-Encoding 首部字段用来告知服务器用户代理支持的内容编码及内容编码的优先级顺序。可一次性指定多种内容编码

_**1、gzip**_

由文件压缩程序gzip（GNU zip）生成的编码格式（RFC1952），采用Lempel-Ziv 算法（LZ77） 及32 位循环冗余校验（CyclicRedundancy Check，通称CRC）。

_**2、compress**_

由UNIX 文件压缩程序compress 生成的编码格式，采用Lempel-Ziv-Welch 算法（LZW）。

_**3、deflate**_

组合使用zlib 格式（RFC1950）及由deflate 压缩算法（RFC1951）生成的编码格式。

_**4、identity**_

不执行压缩或不会变化的默认编码格式



+ **Accept-Language**

首部字段Accept-Language 用来告知服务器用户代理能够处理的自然语言集（指中文或英文等），以及自然语言集的相对优先级。可一次指定多种自然语言集。



+ **Authorization**

首部字段Authorization 是用来告知服务器，用户代理的认证信息（证书值）



+ **Expect**

客户端使用首部字段Expect 来告知服务器，期望出现的某种特定行为。



+ **From**

首部字段From 用来告知服务器使用用户代理的用户的电子邮件地址。 通常，其使用目的就是为了显示搜索引擎等用户代理的负责人的电子邮件联系方式。



+ **Host**

首部字段Host 会告知服务器，请求的资源所处的互联网主机名和端口号。Host 首部字段在HTTP/1.1 规范内是唯一一个必须被包含在请求内的首部字段。



+ **If-Match**

形如If-xxx 这种样式的请求首部字段，都可称为条件请求。服务器接收到附带条件的请求后，只有判断指定条件为真时，才会执行请求。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548834260584-13d71b58-4575-43e3-b086-b3bde2f88f2c.png)



+ **If-Modified-Since**

首部字段If-Modified-Since，属附带条件之一，它会告知服务器若If-Modified-Since 字段值早于资源的更新时间，则希望能处理该请求。



+ **If-None-Match**

首部字段If-None-Match 属于附带条件之一。它和首部字段If-Match 作用相反。用于指定If-None-Match 字段值的实体标记（ETag）值与请求资源的ETag 不一致时，它就告知服务器处理该请求。



+ **If-Range**

首部字段If-Range 属于附带条件之一。它告知服务器若指定的If-Range 字段值（ETag 值或者时间）和请求资源的ETag 值或时间相一致时，则作为范围请求处理。反之，则返回全体资源。



+ **If-Unmodified-Since**

首部字段If-Unmodified-Since 和首部字段If-Modified-Since 的作用相反。它的作用的是告知服务器，指定的请求资源只有在字段值内指定的日期时间之后，未发生更新的情况下，才能处理请求。如果在指定日期时间后发生了更新，则以状态码412 Precondition Failed 作为响应返回。



+ **Max-Forwards**

通过TRACE 方法或OPTIONS 方法， 发送包含首部字段Max-Forwards 的请求时，该字段以十进制整数形式指定可经过的服务器最大数目。服务器在往下一个服务器转发请求之前，Max-Forwards 的值减1 后重新赋值。当服务器接收到Max-Forwards 值为0 的请求时，则不再进行转发，而是直接返回响应。



+ **Proxy-Authorization**

接收到从代理服务器发来的认证质询时，客户端会发送包含首部字段Proxy-Authorization 的请求，以告知服务器认证所需要的信息。



+ **Range**

首部字段Range 即可告知服务器资源的指定范围。



+ **Refer**

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548835344073-8d8d572c-281f-4037-9a29-4c2d1dc80396.png)

****

首部字段Referer 会告知服务器请求的原始资源的URI。

客户端一般都会发送Referer 首部字段给服务器。但当直接在浏览器的地址栏输入URI，或出于安全性的考虑时，也可以不发送该首部字段。



+ **TE**

首部字段TE 会告知服务器客户端能够处理响应的传输编码方式及相对优先级。它和首部字段Accept-Encoding 的功能很相像，但是用于传输编码。



+ **User-Agent**

首部字段User-Agent 会将创建请求的浏览器和用户代理名称等信息传达给服务器。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548836767596-bbfea672-79e0-4e6a-a4aa-88f05ec186df.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#6ede76f4)7、响应首部字段
响应首部字段是由服务器端向客户端返回响应报文中所使用的字段，用于补充响应的附加信息、服务器信息，以及对客户端的附加要求等信息。

+ **Accept-Ranges**

首部字段Accept-Ranges 是用来告知客户端服务器是否能处理范围请求，以指定获取服务器端某个部分的资源。可指定的字段值有两种，可处理范围请求时指定其为bytes，反之则指定其为none。



+ **Age**

首部字段Age 能告知客户端，源服务器在多久前创建了响应。字段值的单位为秒。



+ **ETag**

首部字段ETag 能告知客户端实体标识。它是一种可将资源以字符串形式做唯一性标识的方式。服务器会为每份资源分配对应的ETag 值。

_**ETag 中有强ETag 值和弱ETag 值之分。**_

强ETag 值，不论实体发生多么细微的变化都会改变其值。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548838300951-6e53ed6c-ab6c-4eb6-9335-1bc1ae7726dd.png)

弱ETag 值只用于提示资源是否相同。只有资源发生了根本改变，产生差异时才会改变ETag 值。这时，会在字段值最开始处附加W/。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548838313577-5e5e9a78-d534-4754-847c-730b6bbc46c8.png)



+ **Location**

使用首部字段Location 可以将响应接收方引导至某个与请求URI位置不同的资源。

基本上，该字段会配合3xx ：Redirection 的响应，提供重定向的URI。



+ **Proxy-Authenticate**

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548838382878-2540611a-0e25-43eb-a683-aed2dbcc84c1.png)

首部字段Proxy-Authenticate 会把由代理服务器所要求的认证信息发送给客户端。



+ **Retry-After**

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548838447294-38b0bc08-ad23-4341-b789-d68763a5bf38.png)

首部字段Retry-After 告知客户端应该在多久之后再次发送请求。主要配合状态码503 Service Unavailable 响应，或3xx Redirect 响应一起使用。



+ **Server**

首部字段Server 告知客户端当前服务器上安装的HTTP 服务器应用程序的信息。



+ **Vary**

首部字段Vary 可对缓存进行控制。源服务器会向代理服务器传达关于本地缓存使用方法的命令。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548838685710-e263f740-61fd-4960-8fd9-dde214320c55.png)



+ **WWW-Authenticate******

首部字段WWW-Authenticate 用于HTTP 访问认证。它会告知客户端适用于访问请求URI 所指定资源的认证方案（Basic 或是Digest）和带参数提示的质询（challenge）。状态码401 Unauthorized 响应中，肯定带有首部字段WWW-Authenticate。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#c1afc46a)8、实体首部字段
+ **Allow**

首部字段Allow 用于通知客户端能够支持Request-URI 指定资源的所有HTTP 方法。当服务器接收到不支持的HTTP 方法时，会以状态码405 Method Not Allowed 作为响应返回。



+ **Content-Encoding**

首部字段Content-Encoding 会告知客户端服务器对实体的主体部分选用的内容编码方式。内容编码是指在不丢失实体信息的前提下所进行的压缩。

主要采用以下4 种内容编码的方式：gzip / compress / deflate / identity



+ **Content-Language**

首部字段Content-Language 会告知客户端，实体主体使用的自然语言（指中文或英文等语言）。



+ **Content-Length**

首部字段Content-Length 表明了实体主体部分的大小（单位是字节）。



+ **Content-Location**

首部字段Content-Location 给出与报文主体部分相对应的URI。和首部字段Location 不同，Content-Location 表示的是报文主体返回资源对应的URI。



+ **Content-MD5**

首部字段Content-MD5 是一串由MD5 算法生成的值，其目的在于检查报文主体在传输过程中是否保持完整，以及确认传输到达。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548839307103-50231024-1e60-414f-88ed-255c9c591945.png)



+ **Content-Range**

首部字段Content-Range，能告知客户端作为响应返回的实体的哪个部分符合范围请求。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548839343305-f036dc5c-7d70-4fd0-97d6-e098bff8db87.png)



+ **Content-Type**

首部字段Content-Type 说明了实体主体内对象的媒体类型。和首部字段Accept 一样，字段值用type/subtype 形式赋值。



+ **Expires**

首部字段Expires 会将资源失效的日期告知客户端。



+ **Last-Modified**

首部字段Last-Modified 指明资源最终修改的时间。一般来说，这个值就是Request-URI 指定资源被修改的时间。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#716899bb)9、为Cookies服务的首部字段
Cookie 的工作机制是用户识别及状态管理。Web 网站为了管理用户的状态会通过Web 浏览器，把一些数据临时写入用户的计算机内。接着当用户访问该Web 网站时， 可通过通信方式取回之前发放的Cookie。

调用Cookie 时，由于可校验Cookie 的有效期，以及发送方的域、路径、协议等信息，所以正规发布的Cookie 内的数据不会因来自其他Web 站点和攻击者的攻击而泄露。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548839527869-e11ddb04-46c7-4c8a-b40f-7b472093c43e.png)



+ **SetCookies**

当服务器准备开始管理客户端的状态时，会事先告知各种信息。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548839586281-6ab2f4f4-8d8f-4508-82d8-86eaf002278c.png)![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548839601376-f7851a7e-123d-406d-b015-db84cf0e0ffd.png)



+ **Cookies**

首部字段Cookie 会告知服务器，当客户端想获得HTTP 状态管理支持时，就会在请求中包含从服务器接收到的Cookie。接收到多个Cookie 时，同样可以以多个Cookie 形式发送。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#2ed018f3)10、其他首部字段
+ **X-Frame-Options**

首部字段X-Frame-Options 属于HTTP 响应首部，用于控制网站内容在其他Web 网站的Frame 标签内的显示问题。其主要目的是为了防止点击劫持（clickjacking）攻击。

首部字段X-Frame-Options 有以下两个可指定的字段值。

● DENY ：拒绝

● SAMEORIGIN ：仅同源域名下的页面（Top-level-browsing-context）匹配时许可。（ 比如， 当指定http://hackr.jp/sample.html 页面为SAMEORIGIN 时，那么hackr.jp 上所有页面的frame 都被允许可加载该页面，而example.com 等其他域名的页面就不行了）



+ **X-XSS-Protection**

首部字段X-XSS-Protection 属于HTTP 响应首部，它是针对跨站脚本攻击（XSS）的一种对策，用于控制浏览器XSS 防护机制的开关。

首部字段X-XSS-Protection 可指定的字段值如下。

● 0 ：将XSS 过滤设置成无效状态

● 1 ：将XSS 过滤设置成有效状态



+ **DNT**

首部字段DNT 属于HTTP 请求首部，其中DNT 是Do Not Track的简称，意为拒绝个人信息被收集，是表示拒绝被精准广告追踪的一种方法。

首部字段DNT 可指定的字段值如下。

● 0 ：同意被追踪

● 1 ：拒绝被追踪



+ **P3P**

首部字段P3P 属于HTTP 相应首部，通过利用P3P（The Platformfor Privacy Preferences，在线隐私偏好平台）技术，可以让Web 网站上的个人隐私变成一种仅供程序可理解的形式，以达到保护用户隐私的目的。

要进行P3P 的设定，需按以下操作步骤进行。

步骤1： 创建P3P 隐私

步骤2： 创建P3P 隐私对照文件后，保存命名在/w3c/p3p.xml

步骤3： 从P3P 隐私中新建Compact policies 后，输出到HTTP 响应中



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#3910b078)七、确保Web安全的HTTPS
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#5ed67c02)1、为啥要用HTTPS?
由于HTTP存在的一些不足之处：

●通信使用明文（不加密），内容可能会被窃听

●不验证通信方的身份，因此有可能遭遇伪装

●无法证明报文的完整性，所以有可能已遭篡改



针对HTTP的不足，采用HTTP+加密+认证+完整性保护=HTTPS

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548923300467-ccb0356c-f5b6-4ba8-be3d-e046f3876fef.png)

## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#2379b5bc)2、加密机制有哪些？
SSL 采用一种叫做公开密钥加密（Public-key cryptography）的加密处理方式。

**公开密钥加密：**

使用一对非对称的密钥。一把叫做私有密钥（privatekey），另一把叫做公开密钥（public key）。顾名思义，私有密钥不能让其他任何人知道，而公开密钥则可以随意发布，任何人都可以获得。使用公开密钥加密方式，发送密文的一方使用对方的公开密钥进行加密处理，对方收到被加密的信息后，再使用自己的私有密钥进行解密。利用这种方式，不需要发送用来解密的私有密钥，也不必担心密钥被攻击者窃听而盗走。

**共享密钥加密：**

加密和解密同用一个密钥的方式称为共享密钥加密（Common keycrypto system），也被叫做对称密钥加密。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#bc8bce27)3、HTTPS的加密机制
HTTPS 采用共享密钥加密和公开密钥加密两者并用的混合加密机制。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548924011113-bb854c86-f704-4649-b091-b9cdb0b18a34.png)



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#529a6901)4、HTTP的安全通行机制
![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548924405986-70741ab5-d1fb-42a4-a2f3-023b017749ec.png)



步骤1： 客户端通过发送Client Hello 报文开始SSL 通信。报文中包含客户端支持的SSL 的指定版本、加密组件（CipherSuite）列表（所使用的加密算法及密钥长度等）。



步骤2： 服务器可进行SSL 通信时，会以Server Hello 报文作为应答。和客户端一样，在报文中包含SSL 版本以及加密组件。服务器的加密组件内容是从接收到的客户端加密组件内筛选出来的。



步骤3： 之后服务器发送Certificate 报文。报文中包含公开密钥证书。



步骤4： 最后服务器发送Server Hello Done 报文通知客户端，最初阶段的SSL 握手协商部分结束。



步骤5： SSL 第一次握手结束之后，客户端以Client Key Exchange报文作为回应。报文中包含通信加密中使用的一种被称为Pre-master secret 的随机密码串。该报文已用步骤3 中的公开密钥进行加密。



步骤6： 接着客户端继续发送Change Cipher Spec 报文。该报文会提示服务器，在此报文之后的通信会采用Pre-master secret密钥加密。



步骤7： 客户端发送Finished 报文。该报文包含连接至今全部报文的整体校验值。这次握手协商是否能够成功，要以服务器是否能够正确解密该报文作为判定标准。



步骤8： 服务器同样发送Change Cipher Spec 报文。



步骤9： 服务器同样发送Finished 报文。



步骤10： 服务器和客户端的Finished 报文交换完毕之后，SSL 连接就算建立完成。当然，通信会受到SSL 的保护。从此处开始进行应用层协议的通信，即发送HTTP 请求。



步骤11： 应用层协议通信，即发送HTTP 响应。



步骤12： 最后由客户端断开连接。断开连接时，发送close_notify报文。上图做了一些省略，这步之后再发送TCP FIN 报文来关闭与TCP的通信。



**下面是对整个流程的图解。图中说明了从仅使用服务器端的公开密钥证书（服务器证书）建立HTTPS 通信的整个过程。**

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548924464238-55b10601-0049-439e-a52e-460ad2e9ec0f.png)



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#8cf33ef2)八、确认访问用户身份的认证


HTTP/1.1 使用的认证方式如下所示。

+ **BASIC认证（基本认证）**
+ **DIGEST认证（摘要认证）**
+ **SSL客户端认证**
+ **FormBase认证（基于表单认证）**



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#042b48ca)1、BASIC 认证
认证步骤：

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548925451667-072ee73c-c3f7-4a93-b4c4-f285ef5adf2c.png)

步骤1： 当请求的资源需要BASIC 认证时，服务器会随状态码401Authorization Required， 返回带WWW-Authenticate 首部字段的响应。该字段内包含认证的方式（BASIC） 及Request-URI 安全域字符串（realm）。



步骤2： 接收到状态码401 的客户端为了通过BASIC 认证，需要将用户ID 及密码发送给服务器。发送的字符串内容是由用户ID 和密码构成，两者中间以冒号（:）连接后，再经过Base64 编码处理。

假设用户ID 为guest，密码是guest，连接起来就会形成guest:guest 这样的字符串。然后经过Base64 编码，最后的结果即是Z3Vlc3Q6Z3Vlc3Q=。把这串字符串写入首部字段Authorization 后，发送请求。

当用户代理为浏览器时，用户仅需输入用户ID 和密码即可，之后，浏览器会自动完成到Base64 编码的转换工作。



步骤3： 接收到包含首部字段Authorization 请求的服务器，会对认

证信息的正确性进行验证。如验证通过，则返回一条包含

Request-URI 资源的响应。



缺点：

1. 在HTTP 等非加密通信的线路上进行BASIC 认证的过程中，如果被人窃听，被盗的可能性极高。
2. 一般的浏览器却无法实现认证注销操作。
3. BASIC 认证使用上不够便捷灵活，且达不到多数Web 网站期望的安全性等级



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#099baefb)2、DIGEST 认证
DIGEST 认证同样使用质询/ 响应的方式（challenge/response），但不会像BASIC 认证那样直接发送明文密码。



**质询响应方式：**

一开始一方会先发送认证要求给另一方，接着使用从另一方那接收到的质询码计算生成响应码。最后将响应码返回给对方进行认证的方式。



**认证步骤：**

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548926006926-07dc4e2a-d9d6-422a-b0ad-93c00c5d7199.png)







步骤1： 请求需认证的资源时，服务器会随着状态码401 AuthorizationRequired，返回带WWW-Authenticate 首部字段的响应。该字段内包含质问响应方式认证所需的临时质询码（随机数，nonce）。

首部字段WWW-Authenticate 内必须包含realm 和nonce这两个字段的信息。客户端就是依靠向服务器回送这两个

值进行认证的。nonce 是一种每次随返回的401 响应生成的任意随机字符串。该字符串通常推荐由Base64 编码的十六进制数的组成形式，但实际内容依赖服务器的具体实现。



步骤2： 接收到401 状态码的客户端，返回的响应中包含DIGEST认证必须的首部字段Authorization 信息。首部字段Authorization 内必须包含username、realm、nonce、uri 和response 的字段信息。其中，realm 和nonce就是之前从服务器接收到的响应中的字段。username 是realm 限定范围内可进行认证的用户名。uri（digest-uri）即Request-URI 的值，但考虑到经代理转发后Request-URI 的值可能被修改，因此事先会复制一份副本保存在uri 内。response 也可叫做Request-Digest，存放经过MD5 运算后的密码字符串，形成响应码。响应中其他的实体请参见第6 章的请求首部字段Authorization。另外，有关Request-Digest 的计算规则较复杂，有兴趣的读者不妨深入学习下RFC2617。



步骤3： 接收到包含首部字段Authorization 请求的服务器，会确认认证信息的正确性。认证通过后则返回包含Request-URI资源的响应。并且这时会在首部字段Authentication-Info 写入一些认证成功的相关信息。

DIGEST 认证提供了高于BASIC 认证的安全等级，但是和HTTPS 的客户端认证相比仍旧很弱。DIGEST 认证提供防

止密码被窃听的保护机制，但并不存在防止用户伪装的保护机制。

DIGEST 认证和BASIC 认证一样，使用上不那么便捷灵活，且仍达不到多数Web 网站对高度安全等级的追求标准。因此它的适用范围也有所受限



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#d3069e4a)3、SSL 认证
步骤1： 接收到需要认证资源的请求，服务器会发送CertificateRequest 报文，要求客户端提供客户端证书。



步骤2： 用户选择将发送的客户端证书后，客户端会把客户端证书信息以Client Certificate 报文方式发送给服务器。



步骤3： 服务器验证客户端证书验证通过后方可领取证书内客户端的公开密钥，然后开始HTTPS 加密通信。



## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#7f88a699)4、基于表单认证
一般会使用Cookie 来管理Session（会话），以弥补HTTP 协议中不存在的状态管理功能。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1548926648664-efe4f14e-197c-4e9d-931c-813c5f3aa737.png)

步骤1： 客户端把用户ID 和密码等登录信息放入报文的实体部分，通常是以POST 方法把请求发送给服务器。而这时，会使用HTTPS 通信来进行HTML 表单画面的显示和用户输入数据的发送。



步骤2： 服务器会发放用以识别用户的Session ID。通过验证从客户端发送过来的登录信息进行身份认证，然后把用户的认证状态与Session ID 绑定后记录在服务器端。向客户端返回响应时，会在首部字段Set-Cookie 内写入Session ID（如PHPSESSID=028a8c…）。你可以把Session ID 想象成一种用以区分不同用户的等位号。然而，如果Session ID 被第三方盗走，对方就可以伪装成你的身份进行恶意操作了。因此必须防止Session ID 被盗，或被猜出。为了做到这点，Session ID 应使用难以推测的字符串，且服务器端也需要进行有效期的管理，保证其安全性。另外，为减轻跨站脚本攻击（XSS）造成的损失，建议事先在Cookie 内加上httponly 属性。



步骤3： 客户端接收到从服务器端发来的Session ID 后，会将其作为Cookie 保存在本地。下次向服务器发送请求时，浏览器会自动发送Cookie，所以Session ID 也随之发送到服务器。服务器端可通过验证接收到的Session ID 识别用户和其认证状态。



# [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#6b744736)十一、Web的攻击技术
## [](https://www.yuque.com/jiansuan/osoai6/kg1vz4#16f91b61)1、Web的攻击模式的分类
分为**主动攻击**和**被动攻击**

**1、主动攻击——以服务器为目标的主动攻击**

主动攻击（active attack）是指攻击者通过直接访问Web 应用，把攻击代码传入的攻击模式。

主动攻击模式里具有代表性的攻击是SQL 注入攻击和OS 命令注入攻击。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1549007729152-2e58763c-e750-4378-a1cb-59e640ef9572.png)



**2、被动攻击 —— 以服务器为目标的被动攻击**

被动攻击（passive attack）是指利用圈套策略执行攻击代码的攻击模式。

被动攻击通常的攻击模式：

步骤1： 攻击者诱使用户触发已设置好的陷阱，而陷阱会启动发送已嵌入攻击代码的HTTP 请求。

步骤2： 当用户不知不觉中招之后，用户的浏览器或邮件客户端就会触发这个陷阱。

步骤3： 中招后的用户浏览器会把含有攻击代码的HTTP 请求发送给作为攻击目标的Web 应用，运行攻击代码。

步骤4： 执行完攻击代码，存在安全漏洞的Web 应用会成为攻击者的跳板，可能导致用户所持的Cookie 等个人信息被窃取，登录状态中的用户权限遭恶意滥用等后果。被动攻击模式中具有代表性的攻击是跨站脚本攻击和跨站点请求伪造。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1549007965353-b33f188e-a49d-4f28-8471-98c9da6cc106.png)



**3、利用用户的身份攻击企业内部网络**

利用被动攻击，可发起对原本从互联网上无法直接访问的企业内网等网络的攻击。

很多企业内网依然可以连接到互联网上，访问Web 网站，或接收互联网发来的邮件。这样就可能给攻击者以可乘之机，诱导用户触发陷阱后对企业内网发动攻击。

![](https://cdn.nlark.com/yuque/0/2019/png/111898/1549008212771-c50c12ec-61c6-4f46-b2e2-9f9d42a66d13.png)

