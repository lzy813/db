# 一、数据库概述

## 1、为什么要使用数据库

- **持久化 (persistence)**：<font color="red">**把数据保存到可掉电式存储设备中以供之后使用**</font>。大多数情况下，特别是企业级应用，<font color="red">**数据持久化意味着将内存中的数据保存到硬盘上加以 “固化”**</font>，而持久化的实现过程大多通过各种关系数据库来完成。
- 持久化的主要作用是<font color="red">**将内存中的数据存储在关系型数据库中**</font>，当然也可以存储在磁盘文件、XML 数据文件中。

![持久化](图片/基础/概述/持久化.png)



## 2、数据库与数据库管理系统

### 2.1 相关概念

|      名称      |                简称                |                             作用                             |
| :------------: | :--------------------------------: | :----------------------------------------------------------: |
|     数据库     |           DataBase（DB）           | 即存储数据的 “仓库”，其本质是一个文件系统。它保存了一系列有组织的数据。 |
| 数据库管理系统 | DataBase Management System（DBMS） | 是一种操纵和管理数据库的大型软件，用于建立、使用和维护数据库，对数据库进行统一管理和控制。用户通过数据库管理系统访问数据库中表内的数据 |
|      SQL       |  Structured Query Language（SQL）  | 操作关系型数据库的编程语言，定义了一套操作关系型数据库统一**标准** |



### 2.2 数据库与数据库管理系统关系

- 数据库管理系统 (DBMS) 可以管理多个数据库，一般开发人员会针对每一个应用创建一个数据库。为保存应用中实体的数据，一般会在数据库创建多个表，以保存程序中实体用户的数据。
- 数据库管理系统、数据库和表的关系如图

![关系1](图片/基础/概述/关系1.png)

![关系2](图片/基础/概述/关系2.png)

### 2.3 常见数据库排名

- 排名：https://db-engines.com/en/ranking

- 走势图：https://db-engines.com/en/ranking_trend



### 2.4 常见数据库

- <font color="red">**Oracle**</font>：它是第一个商用的 RDBMS（关系型数据库管理系统）。随着 Oracle 软件的名气越来越大，公司也改名叫 Oracle 公司。此前的 2008 年，SUN 以 10 亿美金收购 MySQL。意味着 Oracle 同时拥有了 MySQL 的管理权，至此 Oracle 在数据库领域中成为绝对的领导者。2013 年，甲骨文超越 IBM，成为继 Microsoft 后全球第二大软件公司。
- <font color="red">**SQL Server**</font>：SQL Server 是微软开发的大型商业数据库，诞生于 1989 年。C#、.net 等语言常使用，与 WinNT 完全集成，也可以很好地与 Microsoft BackOffice 产品集成。
- <font color="red">**DB2**</font>：IBM 公司的数据库产品，收费的。常应用在银行系统中
- <font color="red">**PostgreSQL**</font>：PostgreSQL 的稳定性极强，最符合 SQL 标准，开放源码，具备商业级 DBMS 质量。PG 对数据量大的文本以及 SQL 处理表现较好
- <font color="red">**SyBase**</font>：已经淡出历史舞台。提供了一个非常专业数据建模的工具 PowerDesigner。
- <font color="red">**SQLite**</font>：嵌入式的小型数据库，应用在手机端。零配置，SQLite3 不用安装，不用配置，不用启动，关闭或者配置数据库实例。当系统崩溃后不用做任何恢复操作，再下次使用数据库的时候自动恢复
- <font color="red">**informix**</font>：IBM 公司出品，取自 Information 和 Unix 的结合，它是第一个被移植到 Linux 上的商业数据库产品。仅运行于 unix\linux 平台，命令行操作。性能较高，支持集群，适应于安全性要求极高的系统，尤其是银行，证券系统的应用。





## 3、MySQL

### 3.1 概述

- MySQL 是一个<font color="red">**开放源代码的关系型数据库管理系统**</font>，由瑞典 MySQL AB（创始人 Michael Widenius）公司 1995 年开发，迅速成为开源数据库的 No.1。
- 2008 被 <font color="red">**Sun**</font> 收购（10 亿美金），2009 年 Sun 被 <font color="red">**Oracle**</font> 收购。<font color="red">**MariaDB**</font>应运而生。（MySQL 的创造者担心 MySQL 有闭源的风险，因此创建了 MySQL 的分支项目 MariaDB）
- MySQL 6.x 版本之后分为<font color="red">**社区版**</font>和<font color="red">**商业版**</font>
- MySQL 是一种关联数据库管理系统，将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。
- MySQL 是开源的，所以你不需要支付额外的费用。
- MySQL 是可以定制的，采用了 <font color="red">**GPL（GNU General Public License）**</font>协议，你可以修改源码来开发自己的 MySQL 系统。
- MySQL 支持大型的数据库。可以处理拥有上千万条记录的大型数据库。
- MySQL 支持大型数据库，支持 5000 万条记录的数据仓库，32 位系统表文件最大可支持 <font color="red">**4GB**</font>，64 位系统支持最大的表文件为 <font color="red">**8TB**</font>
- MySQL 使用<font color="red">**标准的 SQL 数据语言**</font>形式。
- MySQL 可以允许运行于多个系统上，并且支持多种语言。这些编程语言包括 C、C++、Python、Java、Perl、PHP 和 Ruby 等



### 3.2 优点

- 开放源代码，使用成本低。
- 性能卓越，服务稳定。
- 软件体积小，使用简单，并且易于维护。
- 历史悠久，社区用户非常活跃，遇到问题可以寻求帮助。
- 许多互联网公司在用，经过了时间的验证



### 3.3 Oracle和MySQL

- Oracle 更适合大型跨国企业的使用，因为他们对费用不敏感，但是<font color="red">**对性能要求以及安全性有更高**</font>的要求。
- MySQL 由于其<font color="red">**体积小、速度快、总体拥有成本低，可处理上千万条记录的大型数据库，尤其是开放源码这一特点，使得很多互联网公司、中小型网站选择了 MySQL 作为网站数据库**</font>（Facebook，Twitter，YouTube，阿里巴巴 \ 蚂蚁金服，去哪儿，美团外卖，腾讯）



## 4、RDBMS与非RDBMS

### 4.1 关系型数据库

#### 4.1.1 实质

- 这种类型的数据库是**最古老**的数据库类型，关系型数据库模型是把复杂的数据结构归结为简单的<font color="red">**二元关系（即二维表格形式）**</font>
- 关系型数据库以<font color="red">**行 (row)和列 (column)**</font>的形式存储数据，以便于用户理解。这一系列的行和列被称为<font color="red">**表 (table)**</font>，一组表组成了一个<font color="red">**库 (database)**</font>
- 表与表之间的数据记录有关系 (relationship)。现实世界中的各种实体以及实体之间的各种联系均用<font color="red">**关系模型**</font>来表示。关系型数据库，就是建立在<font color="red">**关系模型**</font>基础上的数据库。
- SQL 就是关系型数据库的查询语言。

![关系型数据库](图片/基础/概述/关系型数据库.png)



#### 4.1.2 优势

- <font color="red">**复杂查询**</font>：可以用 SQL 语句方便地在一个表以及多个表之间做非常复杂的数据查询。
- <font color="red">**事务支持**</font>：使得对于安全性能很高的数据访问要求得以实现。



### 4.2 非关系型数据库

#### 4.2.1 介绍

- **非关系型数据库**，可看成传统关系型数据库的功能阉割版本，基于键值对存储数据，不需要经过 SQL 层的解析，<font color="red">**性能非常高**</font>。同时，通过减少不常用的功能，进一步提高性能。
- 目前基本上大部分主流的非关系型数据库都是免费的



#### 4.2.2 有哪些非关系型数据库

- 相比于 SQL，**NoSQL**泛指非关系型数据库，包括了榜单上的键值型数据库、文档型数据库、搜索引擎和列存储等，除此以外还包括图形数据库。也只有用 NoSQL 一词才能将这些技术囊括进来。

- <font color="red">**键值型数据库**</font>

  - 键值型数据库通过 Key-Value 键值的方式来存储数据，其中 Key 和 Value 可以是简单的对象，也可以是复杂的对象。Key 作为唯一的标识符，优点是查找速度快，在这方面明显优于关系型数据库，缺点是无法像关系型数据库一样使用条件过滤（比如 WHERE），如果你不知道去哪里找数据，就要遍历所有的键，这就会消耗大量的计算。
  - 键值型数据库典型的使用场景是作为**内存缓存**。**Redis**是最流行的键值型数据库

- <font color="red">**文档型数据库**</font>

  - 此类数据库可存放并获取文档，可以是 XML、JSON 等格式。在数据库中文档作为处理信息的基本单位，一个文档就相当于一条记录。文档数据库所存放的文档，就相当于键值数据库所存放的 “值”。
  - MongoDB 是最流行的文档型数据库。此外，还有 CouchDB 等。

- <font color="red">**搜索引擎数据库**</font>

  - 虽然关系型数据库采用了索引提升检索效率，但是针对全文索引效率却较低。搜索引擎数据库是应用在搜索引擎领域的数据存储形式，由于搜索引擎会爬取大量的数据，并以特定的格式进行存储，这样在检索的时候才能保证性能最优。核心原理是 “倒排索引”。
  - 典型产品：Solr、Elasticsearch、Splunk 等。

- <font color="red">**列式数据库**</font>

  - 列式数据库是相对于行式存储的数据库，Oracle、MySQL、SQL Server 等数据库都是采用的行式存储（Row-based），而列式数据库是将数据按照列存储到数据库中，这样做的好处是可以大量降低系统的 I\O，适合于分布式文件系统，不足在于功能相对有限。典型产品：HBase 等

  ![列式数据库](图片/基础/概述/列式数据库.png)

- <font color="red">**图形数据库**</font>

  - 图形数据库，利用了图这种数据结构存储了实体（对象）之间的关系。图形数据库最典型的例子就是社交网络中人与人的关系，数据模型主要是以节点和边（关系）来实现，特点在于能高效地解决复杂的关系问题。
  - 图形数据库顾名思义，就是一种存储图形关系的数据库。它利用了图这种数据结构存储了实体（对象）之间的关系。关系型数据用于存储明确关系的数据，但对于复杂关系的数据存储却有些力不从心。如社交网络中人物之间的关系，如果用关系型数据库则非常复杂，用图形数据库将非常简单。典型产品：Neo4J、InfoGrid 等



### 4.3 小结

- NoSQL 的分类很多，即便如此，在 DBMS 排名中，还是 SQL 阵营的比重更大，影响力前 5 的 DBMS 中有 4 个是关系型数据库，而排名前 20 的 DBMS 中也有 12 个是关系型数据库。所以说，掌握 SQL 是非常有必要的。
- NoSQL 对 SQL 做出了很好的补充，比如实际开发中，有很多业务需求，其实并不需要完整的关系型数据库功能，非关系型数据库的功能就足够使用了。这种情况下，使用<font color="red">**性能更高**</font>、<font color="red">**成本更低**</font>的非关系型数据库当然是更明智的选择。比如：日志收集、排行榜、定时器等。



## 5、关系型数据库设计规则

- 关系型数据库的典型数据结构就是<font color="red">**数据表**</font>，这些数据表的组成都是结构化的（Structured）
- 将数据放到表中，表再放到库中
- 一个数据库中可以有多个表，每个表都有一个名字，用来标识自己。表名具有唯一性
- 表具有一些特性，这些特性定义了数据在表中如何存储，类似 Java 和 Python 中 “类” 的设计



### 5.1 表、记录、字段

- E-R（entity-relationship，实体 - 联系）模型中有三个主要概念是：<font color="red">**实体集**、**属性**、**联系集**</font>
- 一个实体集（class）对应于数据库中的一个表（table），一个实体（instance）则对应于数据库表中的一行（row），也称为一条<font color="red">**记录（record）**</font>。一个属性（attribute）对应于数据库表中的一列（column），也称为一个<font color="red">**字段（field）**</font>



### 5.2 表的关联关系

- 表与表之间的数据记录有关系 (relationship)。现实世界中的各种实体以及实体之间的各种联系均用关系模型来表示。
- 四种：**一对一关联**、**一对多关联**、**多对多关联**、**自我引用**



#### 5.2.1 一对一关联

- one-to-one

- 在实际的开发中应用不多，因为一对一可以创建成一张表。
- 举例：设计学生表：学号、姓名、手机号码、班级、系别、身份证号码、家庭住址、籍贯、紧急联系人、…
  - 拆为两个表：两个表的记录是一一对应关系。
  - 基础信息表（常用信息）：学号、姓名、手机号码、班级、系别
  - 档案信息表（不常用信息）：学号、身份证号码、家庭住址、籍贯、紧急联系人、…
- 两种建表原则：
  - 外键唯一：主表的主键和从表的外键（唯一），形成主外键关系，外键唯一。
  - 外键是主键：主表的主键和从表的主键，形成主外键关系。



#### 5.2.2 一对多关系

- one-to-many

- 常见实例场景：**客户表和订单表**，**分类表和商品表**，**部门表和员工表**。
- 举例：
  - 员工表：编号、姓名、…、所属部门
  - 部门表：编号、名称、简介
- 一对多建表原则：在<font color="red">**从表（多方）创建一个字段，字段作为外键**</font>指向  主表（一方） 的主键



#### 5.2.3 多对多

- many-to-many

- 要表示多对多关系，必须创建第三个表，该表通常称为<font color="red">**联接表**</font>，它将多对多关系划分为两个一对多关系。将这两个表的主键都插入到第三个表中。
- 举例 1：学生 - 课程
  - 学生信息表：一行代表一个学生的信息（学号、姓名、手机号码、班级、系别…）
  - 课程信息表：一行代表一个课程的信息（课程编号、授课老师、简介…）
  - 选课信息表：一个学生可以选多门课，一门课可以被多个学生选择
- 举例 2：订单 - 产品
  - “订单” 表和 “产品” 表有一种多对多的关系，这种关系是通过与 “订单明细” 表建立两个一对多关系来定义的。一个订单可以有多个产品，每个产品可以出现在多个订单中。
    - 产品表：“产品” 表中的每条记录表示一个产品。
    - 订单表：“订单” 表中的每条记录表示一个订单。
    - 订单明细表：每个产品可以与 “订单” 表中的多条记录对应，即出现在多个订单中。一个订单可以与 “产品” 表中的多条记录对应，即包含多个产品。
- 举例 3：用户 - 角色
  - 多对多关系建表原则：需要创建第三张表，中间表中至少两个字段，这两个字段分别作为外键指向各自一方的主键



#### 5.2.4 自我引用

- Self reference

![自我引用](图片/基础/概述/自我引用.png)



## 6、MySQL的数据模型

- 关系型数据库（RDBMS）
  - 概念：建立在关系模型基础上，由多张相互连接的二维表组成的数据库
  - 特点：
    - 使用表存储数据，格式统一，便于维护
    - 使用SQL语言操作，标准统一，使用方便
- 数据模型
  - 客户端连接上服务器
  - 客户端通过DBMS创建多个数据库
  - 每个数据库里可以创建多张表
  - 每个表里可以存放多条数据![MySQL数据模型](E:/%E7%9F%A5%E8%AF%86/db/MySQL/%E5%9B%BE%E7%89%87/%E5%9F%BA%E7%A1%80/%E6%A6%82%E8%BF%B0/MySQL%E6%95%B0%E6%8D%AE%E6%A8%A1%E5%9E%8B.png)





# 二、环境搭建

## 1、MySQL卸载

- <font color="red">**停止MySQL服务**</font>：按 Win + R 键输入 <font color="red">**services.msc**</font> 打开服务，找到 MySQL（如 MySQL80）右键选择**停止**。

![卸载1](图片/基础/Windows下载安装/卸载1.png)

- <font color="red">**控制面板卸载软件**</font>

![卸载2](图片/基础/Windows下载安装/卸载2.png)

![卸载3](图片/基础/Windows下载安装/卸载3.png)

- <font color="red">**清除残留的文件**</font>

  - 一般默认在这个C盘的文件的位置，这些文件都进行删除

  ~~~bash
  C:\Program Files\MySQL
  ~~~

  ![卸载4](图片/基础/Windows下载安装/卸载4.png)

- <font color="red">**删除注册表内容**</font>

~~~bash
HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\EventLog\Application\MySQLD Service
~~~

![卸载5](图片/基础/Windows下载安装/卸载5.png)

- <font color="red">**删除MySQL环境变量**</font>

![卸载6](图片/基础/Windows下载安装/卸载6.png)



## 2、MySQL的下载与安装

- MySQL 下载地址为：https://dev.mysql.com/downloads/windows/installer/，这里下载的是mysql的msi安装文件，选择下面的470.2M的版本，点击download进行下载。

![1](图片/基础/Windows下载安装/1.png)

- 在下载页面直接选择：**No thanks, just start my download.进行下载**

![2](图片/基础/Windows下载安装/2.png)

- 下载好mysql的msi安装文件后，双击进行安装，选择最下面的Custom模式安装，点击右下角 Next 到下一步

![3](图片/基础/Windows下载安装/3.png)

- 选择MySql Server 8.0.27 移动到右侧，点击Next

![4](图片/基础/Windows下载安装/4.png)

- 点击Execute，检查必要配置

![5](图片/基础/Windows下载安装/5.png)

- 检查过程中，可能会提示要安装微软文件，这时安装即可；等到后面的status提示的状态完成后，点击Next进行下一步

![6](图片/基础/Windows下载安装/6.png)

- 然后，点击Execute执行

![7](图片/基础/Windows下载安装/7.png)

- 此时会进行下载文件

![8](图片/基础/Windows下载安装/8.png)

- 全部下载完成后，Status提示状态Complete表示已完成，此时点击Next

![9](图片/基础/Windows下载安装/9.png)

- 此时到下一步再点击Next

![10](图片/基础/Windows下载安装/10.png)

- 再 Type and NetWorking 页面中，Port是mysql数据库的默认端口3306，直接点击Next

![11](图片/基础/Windows下载安装/11.png)

- 在认证方式页面有两个选项，强密码认证和以前的认证方式，我这里选择的是强密码认证，然后Next

![12](图片/基础/Windows下载安装/12.png)

- 然后输入root用户的密码，密码一定要记住，否则无法登录。

![12](图片/基础/Windows下载安装/13.png)

- 检查mysql的服务，建议使用默认不修改，点击Next

![14](图片/基础/Windows下载安装/14.png)

- 在Apply Configuration 点击Execute执行

![15](图片/基础/Windows下载安装/15.png)

- 应用配置完成后，点击Finish继续

![16](图片/基础/Windows下载安装/16.png)

- 在Product Configuration 中，status提示状态完成后，点击Next继续

![17](图片/基础/Windows下载安装/17.png)

- 最后一步，提示安装完成，点击Finish结束

![18](图片/基础/Windows下载安装/18.png)

- 配置环境变量：在系统用户的path下加上

~~~bash
mysql安装路径/bin
~~~

- 验证

~~~bash
# 查看mysql版本
mysql --version
mysql -V
select version();

# mysql登陆：-p:密码 -h:ip -P:端口
mysql -u root -h localhost -P 3306 -p密码
~~~



## 3、MySQL的开启与关闭

- MySQL的开启与关闭

```bash
net start mysql80						# 启动mysql服务
net stop mysql80						# 关闭mysql服务
# 注意：mysql服务一般是开机自启的
```

- MySQL的客户端连接

```bash
# cmd打开，然后输入命令
# 前提是得配置环境变量，否则得从mysql的安装目录下进入cmd
# mysql登陆：-p:密码 -h:ip -P:端口
mysql -u root -h localhost -P 3306 -p密码

# 退出
quit/exit
```



## 4、字符集编码问题

### 4.1 MySQL5.7

- **问题再现：命令行操作sql乱码问题**

```mysql
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at row 1
```

- **问题解决**

步骤1：查看编码命令

```
show variables like 'character_%';
show variables like 'collation_%';
```

步骤2：修改mysql的数据目录下的my.ini配置文件

```ini
[mysql]  #大概在63行左右，在其下添加
... 
default-character-set=utf8  #默认字符集

[mysqld]  # 大概在76行左右，在其下添加
...
character-set-server=utf8
collation-server=utf8_general_ci
```

> 注意：建议修改配置文件使用notepad++等高级文本编辑器，使用记事本等软件打开修改后可能会导致文件编码修改为“含BOM头”的编码，从而服务重启失败。

步骤3：重启服务

步骤4：查看编码命令

```sql
show variables like 'character_%';
show variables like 'collation_%';
```

![MySQL编码2](图片/基础/Windows下载安装/MySQL编码2.jpg)

* 如果是以上配置就说明对了。接着我们就可以新创建数据库、新创建数据表，接着添加包含中文的数据了。



### 4.2 MySQL8.0中

- 在MySQL 8.0版本之前，默认字符集为latin1，utf8字符集指向的是utf8mb3。网站开发人员在数据库设计的时候往往会将编码修改为utf8字符集。如果遗忘修改默认的编码，就会出现乱码的问题。从MySQL 8.0开始，数据库的默认编码改为`utf8mb4`，从而避免了上述的乱码问题。



## 5、MySQL目录结构与源码

| MySQL的目录结构                             | 说明                                 |
| ------------------------------------------- | ------------------------------------ |
| bin目录                                     | 所有MySQL的可执行文件。如：mysql.exe |
| MySQLInstanceConfig.exe                     | 数据库的配置向导，在安装时出现的内容 |
| data目录                                    | 系统数据库所在的目录                 |
| my.ini文件                                  | MySQL的主要配置文件                  |
| C:\ProgramData\MySQL\MySQL Server 8.0\data\ | 用户创建的数据库所在的目录           |



## 6、常见问题的解决

### 6.1 root密码忘记

1: 通过任务管理器或者服务管理，关掉mysqld(服务进程)
2: 通过命令行+特殊参数开启mysqld
mysqld --defaults-file="D:\ProgramFiles\mysql\MySQLServer5.7Data\my.ini" --skip-grant-tables

3: 此时，mysqld服务进程已经打开。并且不需要权限检查
4: mysql -uroot 无密码登陆服务器。另启动一个客户端进行
5: 修改权限表
（1） use mysql;
（2）update user set authentication_string=password('新密码') where user='root' and Host='localhost'; 
（3）flush privileges;
6: 通过任务管理器，关掉mysqld服务进程。
7: 再次通过服务管理，打开mysql服务。
8: 即可用修改后的新密码登陆。



### 6.2 不是内部或外部命令

- 如果输入mysql命令报“不是内部或外部命令”，把mysql安装目录的bin目录配置到环境变量path中



### 6.3 没有选择数据库

| ERROR 1046 (3D000): No database selected                     |
| ------------------------------------------------------------ |
| 解决方案一：就是使用“USE 数据库名;”语句，这样接下来的语句就默认针对这个数据库进行操作 |
| 解决方案二：就是所有的表对象前面都加上“数据库.”              |



### 6.4 命令行客户端的字符集问题

```mysql
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at row 1
```

- 原因：服务器端认为你的客户端的字符集是utf-8，而实际上你的客户端的字符集是GBK。


- 查看所有字符集：**SHOW VARIABLES LIKE 'character_set_%';**


![字符集问题1](图片/基础/Windows下载安装/字符集问题1.png)

- 解决方案，设置当前连接的客户端字符集 **“SET NAMES GBK;”**


![字符集问题2](图片/基础/Windows下载安装/字符集问题2.png)



### 6.5 修改数据库和表的字符编码

修改编码：

（1)先停止服务，（2）修改my.ini文件（3）重新启动服务

说明：

如果是在修改my.ini之前建的库和表，那么库和表的编码还是原来的Latin1，要么删了重建，要么使用alter语句修改编码。

```mysql
mysql> create database 0728db charset Latin1;
Query OK, 1 row affected (0.00 sec)
```

```
mysql> use 0728db;
Database changed
```

```mysql
mysql> create table student (id int , name varchar(20)) charset Latin1;
Query OK, 0 rows affected (0.02 sec)


mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student` (
  `id` int(11) NOT NULL,
  `name` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1
1 row in set (0.00 sec)
```

```mysql
mysql> alter table student charset utf8; #修改表字符编码为UTF8
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0


mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student` (
  `id` int(11) NOT NULL,
  `name` varchar(20) CHARACTER SET latin1 DEFAULT NULL,  #字段仍然是latin1编码
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
1 row in set (0.00 sec)


mysql> alter table student modify name varchar(20) charset utf8; #修改字段字符编码为UTF8
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0


mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student` (
  `id` int(11) NOT NULL,
  `name` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
1 row in set (0.00 sec)
```

```mysql
mysql> show create database 0728db;;
+--------+-----------------------------------------------------------------+
|Database| Create Database                                                 |
+------+-------------------------------------------------------------------+
|0728db| CREATE DATABASE `0728db` /*!40100 DEFAULT CHARACTER SET latin1 */ |
+------+-------------------------------------------------------------------+
1 row in set (0.00 sec)


mysql> alter database 0728db charset utf8; #修改数据库的字符编码为utf8
Query OK, 1 row affected (0.00 sec)


mysql> show create database 0728db;
+--------+-----------------------------------------------------------------+
|Database| Create Database                                                 |
+--------+-----------------------------------------------------------------+
| 0728db | CREATE DATABASE `0728db` /*!40100 DEFAULT CHARACTER SET utf8 */ |
+--------+-----------------------------------------------------------------+
1 row in set (0.00 sec)
```



# 三、基本SELECT语句

## 1、分类

SQL语言在功能上主要分为如下3大类：

- <font color="red">**DDL（Data Definition Languages、数据定义语言）**</font>，这些语句定义了不同的数据库、表、视图、索引等数据库对象，还可以用来创建、删除、修改数据库和数据表的结构。
  - 主要的语句关键字包括 CREATE、DROP、ALTER、RENAME、TRUNCATE 等。

- <font color="red">**DML（Data Manipulation Language、数据操作语言）**</font>，用于添加、删除、更新和查询数据库记录，并检查数据完整性。
  - 主要的语句关键字包括 INSERT、DELETE、UPDATE、SELECT等。
  - **SELECT是SQL语言的基础，最为重要。**

- <font color="red">**DCL（Data Control Language、数据控制语言）**</font>，用于定义数据库、表、字段、用户的访问权限和安全级别。
  - 主要的语句关键字包括 GRANT、REVOKE、COMMIT、ROLLBACK、SAVEPOINT等。

> 因为查询语句使用的非常的频繁，所以很多人把查询语句单拎出来一类：DQL（数据查询语言）。
>
> 还有单独将COMMIT、ROLLBACK 取出来称为TCL （Transaction Control Language，事务控制语言）。



## 2、SQL规则与规范

### 2.1 基本规则

- SQL 可以写在一行或者多行。为了提高可读性，各子句分行写，必要时使用缩进
- 每条命令以 ; 或 \g 或 \G 结束

~~~sql
mysql> show databases\g
+------------------------+
| Database               |
+------------------------+
| book                   |
| information_schema     |
| library-manager-system |
| mysql                  |
| performance_schema     |
| sys                    |
+------------------------+
6 rows in set (0.02 sec)

mysql> show databases\G
*************************** 1. row ***************************
Database: book
*************************** 2. row ***************************
Database: information_schema
*************************** 3. row ***************************
Database: library-manager-system
*************************** 4. row ***************************
Database: mysql
*************************** 5. row ***************************
Database: performance_schema
*************************** 6. row ***************************
Database: sys
6 rows in set (0.00 sec)
~~~

- 关键字不能被缩写也不能分行
- 关于标点符号
  - 必须保证所有的()、单引号、双引号是成对结束的
  - 必须使用英文状态下的半角输入方式
  - 字符串型和日期时间类型的数据可以使用单引号（' '）表示
  - 列的别名，尽量使用双引号（" "），而且不建议省略as



### 2.2 SQL大小写规范 

- <font color="red">**MySQL 在 Windows 环境下是大小写不敏感的**</font>
- <font color="red">**MySQL 在 Linux 环境下是大小写敏感的**</font>
  - 数据库名、表名、表的别名、变量名是严格区分大小写的
  - 关键字、函数名、列名(或字段名)、列的别名(字段的别名) 是忽略大小写的。
  - 总结：<font color="red">**自定义写的就严格区分，官方提供的就不区分**</font>
- **推荐采用统一的书写规范：**
  - 数据库名、表名、表别名、字段名、字段别名等都小写
  - SQL 关键字、函数名、绑定变量等都大写



### 2.3 注 释

可以使用如下格式的注释结构

```mysql
单行注释：#注释文字(MySQL特有的方式)
单行注释：-- 注释文字(--后面必须包含一个空格。)
多行注释：/* 注释文字  */
```



### 2.4 命名规则

- 数据库、表名不得超过30个字符，变量名限制为29个
- 必须只能包含 A–Z, a–z, 0–9, _共63个字符
- 数据库名、表名、字段名等对象名中间不要包含空格
- 同一个MySQL软件中，数据库不能同名；同一个库中，表不能重名；同一个表中，字段不能重名
- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在SQL语句中使用`（着重号）引起来
- 保持字段名和类型的一致性，在命名字段并为其指定数据类型的时候一定要保证一致性。假如数据类型在一个表里是整数，那在另一个表里可就别变成字符型了

举例：

```mysql
# 以下两句是一样的，不区分大小写
show databases;
SHOW DATABASES;

#创建表格
#create table student info(...); #表名错误，因为表名有空格
create table student_info(...); 

#其中order使用``飘号，因为order和系统关键字或系统函数名等预定义标识符重名了
CREATE TABLE `order`(
    id INT,
    lname VARCHAR(20)
);

select id as "编号", `name` as "姓名" from t_stu; #起别名时，as都可以省略
select id as 编号, `name` as 姓名 from t_stu; #如果字段别名中没有空格，那么可以省略""
select id as 编 号, `name` as 姓 名 from t_stu; #错误，如果字段别名中有空格，那么不能省略""
```



### 2.5 数据导入指令

- 在<font color="red">**命令行客户端登录mysql**</font>，使用source指令导入


```mysql
mysql> source d:\mysqldb.sql
```

```mysql
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field          | Type        | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id    | int(6)      | NO   | PRI | 0       |       |
| first_name     | varchar(20) | YES  |     | NULL    |       |
| last_name      | varchar(25) | NO   |     | NULL    |       |
| email          | varchar(25) | NO   | UNI | NULL    |       |
| phone_number   | varchar(20) | YES  |     | NULL    |       |
| hire_date      | date        | NO   |     | NULL    |       |
| job_id         | varchar(10) | NO   | MUL | NULL    |       |
| salary         | double(8,2) | YES  |     | NULL    |       |
| commission_pct | double(2,2) | YES  |     | NULL    |       |
| manager_id     | int(6)      | YES  | MUL | NULL    |       |
| department_id  | int(4)      | YES  | MUL | NULL    |       |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```



## 3、基本的SELECT语句

### 3.0 SELECT...

```mysql
SELECT 1; #没有任何子句
SELECT 9/2; #没有任何子句
SELECT 9 FROM DUAL;	# DUAL伪表，官方提供的公用方式，没有具体含义，只是为了标准化
```

### 3.1 SELECT ... FROM

- 语法：

```sql
SELECT   标识选择哪些列
FROM     标识从哪个表中选择
```

- 选择全部列：

```sql
SELECT *
FROM departments;
```

- 注意

  - <font color="red">**一般情况下，除非需要使用表中所有的字段数据，最好不要使用通配符‘*’。使用通配符虽然可以节省输入查询语句的时间，但是获取不需要的列数据通常会降低查询和所使用的应用程序的效率。通配符的优势是，当不知道所需要的列的名称时，可以通过它获取它们。**</font>

  - 在生产环境下，不推荐你直接使用 SELECT *进行查询。

- 选择特定的列：

```sql
SELECT department_id, location_id
FROM   departments;
```

> MySQL中的SQL语句是不区分大小写的，因此SELECT和select的作用是相同的，但是，许多开发人员习惯将关键字大写、数据列和表名小写，读者也应该养成一个良好的编程习惯，这样写出来的代码更容易阅读和维护。

### 3.2 列的别名

- 重命名一个列

- 便于计算

- 紧跟列名，也可以<font color="red">**在列名和别名之间加入关键字AS，别名使用双引号**</font>，以便在别名中包含空格或特殊的字符并区分大小写。

- AS 可以省略

- 建议别名简短，见名知意

- 举例

  ```mysql
  SELECT last_name AS "name", commission_pct AS comm
  FROM   employees;
  ```

  ```mysql
  SELECT last_name "Name", salary*12 "Annual Salary"
  FROM   employees;
  ```

### 3.3 去除重复行

默认情况下，查询会返回全部行，包括重复行。

```sql
SELECT department_id
FROM   employees;
```

**在SELECT语句中使用关键字DISTINCT去除重复行**

```sql
SELECT DISTINCT department_id
FROM   employees;
```

针对于：

```mysql
SELECT DISTINCT department_id,salary 
FROM employees;
```

这里有两点需要注意：

1. DISTINCT 需要放到所有列名的前面，如果写成 SELECT salary, DISTINCT department_id FROM employees会报错。
2. DISTINCT 其实是对后面所有列名的组合进行去重，你能看到最后的结果是 74 条，因为这 74 个部门id不同，都有 salary 这个属性值。如果你想要看都有哪些不同的部门（department_id），只需要写 DISTINCT department_id即可，后面不需要再加其他的列名了。

### 3.4 空值参与运算

- 所有运算符或列值遇到null值，运算的结果都为null

```sql
SELECT employee_id,salary,commission_pct,
12 * salary * (1 + commission_pct) "annual_sal"
FROM employees;
```

这里你一定要注意，在 MySQL 里面， 空值不等于空字符串。一个空字符串的长度是 0，而一个空值的长度是空。而且，在 MySQL 里面，空值是占用空间的。

### 3.5 着重号

- 错误的

```mysql
mysql> SELECT * FROM ORDER;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ORDER' at line 1
```

- 正确的

```mysql
mysql> SELECT * FROM `ORDER`;
+----------+------------+
| order_id | order_name |
+----------+------------+
|        1 | shkstart   |
|        2 | tomcat     |
|        3 | dubbo      |
+----------+------------+
3 rows in set (0.00 sec)

mysql> SELECT * FROM `order`;
+----------+------------+
| order_id | order_name |
+----------+------------+
|        1 | shkstart   |
|        2 | tomcat     |
|        3 | dubbo      |
+----------+------------+
3 rows in set (0.00 sec)
```

- 结论：<font color="red">**我们需要保证表中的字段、表名等没有和保留字、数据库系统或常用方法冲突。如果真的相同，请在SQL语句中使用一对``（着重号）引起来**</font>

### 3.6 查询常数

- SELECT 查询还可以对常数进行查询。对的，就是在 SELECT 查询结果中增加一列固定的常数列。这列的取值是我们指定的，而不是从数据表中动态取出的。


- SQL 中的 SELECT 语法的确提供了这个功能，一般来说我们只从一个表中查询数据，通常不需要增加一个固定的常数列，但如果我们想整合不同的数据源，用常数列作为这个表的标记，就需要查询常数。


- 比如说，我们想对 employees 数据表中的员工姓名进行查询，同时增加一列字段`corporation`，这个字段固定值为“lzy”，可以这样写：


```mysql
SELECT 'lzy' as name, last_name FROM employees;
```



## 4、显示表结构

使用DESCRIBE 或 DESC 命令，表示表结构。

```mysql
DESCRIBE employees;
或
DESC employees;
```

```mysql
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field          | Type        | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id    | int(6)      | NO   | PRI | 0       |       |
| first_name     | varchar(20) | YES  |     | NULL    |       |
| last_name      | varchar(25) | NO   |     | NULL    |       |
| email          | varchar(25) | NO   | UNI | NULL    |       |
| phone_number   | varchar(20) | YES  |     | NULL    |       |
| hire_date      | date        | NO   |     | NULL    |       |
| job_id         | varchar(10) | NO   | MUL | NULL    |       |
| salary         | double(8,2) | YES  |     | NULL    |       |
| commission_pct | double(2,2) | YES  |     | NULL    |       |
| manager_id     | int(6)      | YES  | MUL | NULL    |       |
| department_id  | int(4)      | YES  | MUL | NULL    |       |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```

其中，各个字段的含义分别解释如下：

- Field：表示字段名称。 
- Type：表示字段类型，这里 barcode、goodsname 是文本型的，price 是整数类型的。
- Null：表示该列是否可以存储NULL值。
- Key：表示该列是否已编制索引。PRI表示该列是表主键的一部分；UNI表示该列是UNIQUE索引的一部分；MUL表示在列中某个给定值允许出现多次。
- Default：表示该列是否有默认值，如果有，那么值是多少。
- Extra：表示可以获取的与给定列有关的附加信息，例如AUTO_INCREMENT等。



## 5、过滤数据

- 语法：

- ```mysql
  SELECT 字段1,字段2
  FROM 表名
  WHERE 过滤条件
  ```

  - <font color="red">**使用WHERE 子句，将不满足条件的行过滤掉**</font>
  - <font color="red">**WHERE子句紧随 FROM子句**</font>

- 举例


```sql
SELECT employee_id, last_name, job_id, department_id
FROM   employees
WHERE  department_id = 90;
```



# 四、运算符

## 1、算术运算符

- 算术运算符主要用于数学运算，其可以连接运算符前后的两个数值或表达式，对数值或表达式进行加（+）、减（-）、乘（*）、除（/）和取模（%）运算。


![算术运算符](图片/基础/运算符/算术运算符.png)

**1．加法与减法运算符**

```mysql
mysql> SELECT 100, 100 + 0, 100 - 0, 100 + 50, 100 + 50 -30, 100 + 35.5, 100 - 35.5 FROM dual;
+-----+---------+---------+----------+--------------+------------+------------+
| 100 | 100 + 0 | 100 - 0 | 100 + 50 | 100 + 50 -30 | 100 + 35.5 | 100 - 35.5 |
+-----+---------+---------+----------+--------------+------------+------------+
| 100 |     100 |     100 |      150 |          120 |      135.5 |       64.5 |
+-----+---------+---------+----------+--------------+------------+------------+
1 row in set (0.00 sec)
```

由运算结果可以得出如下结论：

> - 一个整数类型的值对整数进行加法和减法操作，结果还是一个整数；
> - 一个整数类型的值对浮点数进行加法和减法操作，结果是一个浮点数；
> - 加法和减法的优先级相同，进行先加后减操作与进行先减后加操作的结果是一样的；
> - 在Java中，+的左右两边如果有字符串，那么表示字符串的拼接。但是在MySQL中+只表示数值相加。如果遇到非数值类型，先尝试转成数值，如果转失败，就按0计算。（补充：MySQL中字符串拼接要使用字符串函数CONCAT()实现）

**2．乘法与除法运算符**

```mysql
mysql> SELECT 100, 100 * 1, 100 * 1.0, 100 / 1.0, 100 / 2,100 + 2 * 5 / 2,100 /3, 100 DIV 0 FROM dual;
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
| 100 | 100 * 1 | 100 * 1.0 | 100 / 1.0 | 100 / 2 | 100 + 2 * 5 / 2 | 100 /3  | 100 DIV 0 |
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
| 100 |     100 |     100.0 |  100.0000 | 50.0000 |        105.0000 | 33.3333 |      NULL |
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
1 row in set (0.00 sec)
```

```mysql
#计算出员工的年基本工资
SELECT employee_id,salary,salary * 12 annual_sal 
FROM employees;
```

由运算结果可以得出如下结论：

> - 一个数乘以整数1和除以整数1后仍得原数；
> - 一个数乘以浮点数1和除以浮点数1后变成浮点数，数值与原数相等；
> - 一个数除以整数后，不管是否能除尽，结果都为一个浮点数；
> - 一个数除以另一个数，除不尽时，结果为一个浮点数，并保留到小数点后4位；
> - 乘法和除法的优先级相同，进行先乘后除操作与先除后乘操作，得出的结果相同。
> - 在数学运算中，0不能用作除数，在MySQL中，一个数除以0为NULL。

**3．求模（求余）运算符**
将t22表中的字段i对3和5进行求模（求余）运算。

```mysql
mysql> SELECT 12 % 3, 12 MOD 5 FROM dual;
+--------+----------+
| 12 % 3 | 12 MOD 5 |
+--------+----------+
|      0 |        2 |
+--------+----------+
1 row in set (0.00 sec)
```

```mysql
#筛选出employee_id是偶数的员工
SELECT * FROM employees
WHERE employee_id MOD 2 = 0;
```

可以看到，100对3求模后的结果为3，对5求模后的结果为0。



## 2、比较运算符

比较运算符用来对表达式左边的操作数和右边的操作数进行比较，比较的结果为真则返回1，比较的结果为假则返回0，其他情况则返回NULL。

比较运算符经常被用来作为SELECT查询语句的条件来使用，返回符合条件的结果记录。

![比较运算符1](图片/基础/运算符/比较运算符1.png)

![比较运算符2](图片/基础/运算符/比较运算符2.png)

**1．等号运算符**

- 等号运算符（=）判断等号两边的值、字符串或表达式是否相等，如果相等则返回1，不相等则返回0。

- 在使用等号运算符时，遵循如下规则：
  - 如果等号两边的值、字符串或表达式都为字符串，则MySQL会按照字符串进行比较，其比较的是每个字符串中字符的ANSI编码是否相等。
  - <font color="red">**字符串存在隐式转换，如果转换数值不成功，则看作0参与运算**</font>，如0 = 'abc'为1
  - 如果等号两边的值都是整数，则MySQL会按照整数来比较两个值的大小。
  - 如果等号两边的值一个是整数，另一个是字符串，则MySQL会将字符串转化为数字进行比较。
  - 如果等号两边的值、字符串或表达式中有一个为NULL，则比较结果为NULL。

- 对比：SQL中赋值符号使用 := 

```mysql
mysql> SELECT 1 = 1, 1 = '1', 1 = 0, 'a' = 'a', (5 + 3) = (2 + 6), '' = NULL , NULL = NULL; 
+-------+---------+-------+-----------+-------------------+-----------+-------------+
| 1 = 1 | 1 = '1' | 1 = 0 | 'a' = 'a' | (5 + 3) = (2 + 6) | '' = NULL | NULL = NULL |
+-------+---------+-------+-----------+-------------------+-----------+-------------+
|    1  |     1   |   0   |      1    |             1     |    NULL   |        NULL  |
+-------+---------+-------+-----------+-------------------+-----------+-------------+
1 row in set (0.00 sec)
```

```mysql
mysql> SELECT 1 = 2, 0 = 'abc', 1 = 'abc' FROM dual;
+-------+-----------+-----------+
| 1 = 2 | 0 = 'abc' | 1 = 'abc' |
+-------+-----------+-----------+
|     0 |         1 |         0 |
+-------+-----------+-----------+
1 row in set, 2 warnings (0.00 sec)
```

```mysql
#查询salary=10000，注意在Java中比较是==
SELECT employee_id,salary FROM employees WHERE salary = 10000;
```

**2．安全等于运算符**
安全等于运算符（<=>）与等于运算符（=）的作用是相似的，`唯一的区别`是‘<=>’可以用来对NULL进行判断。在两个操作数均为NULL时，其返回值为1，而不为NULL；当一个操作数为NULL时，其返回值为0，而不为NULL。

```mysql
mysql> SELECT 1 <=> '1', 1 <=> 0, 'a' <=> 'a', (5 + 3) <=> (2 + 6), '' <=> NULL,NULL <=> NULL FROM dual;
+-----------+---------+-------------+---------------------+-------------+---------------+
| 1 <=> '1' | 1 <=> 0 | 'a' <=> 'a' | (5 + 3) <=> (2 + 6) | '' <=> NULL | NULL <=> NULL |
+-----------+---------+-------------+---------------------+-------------+---------------+
|         1 |       0 |           1 |                   1 |           0 |             1 |
+-----------+---------+-------------+---------------------+-------------+---------------+
1 row in set (0.00 sec)
```

```mysql
#查询commission_pct等于0.40
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = 0.40;

SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> 0.40;

#如果把0.40改成 NULL 呢？
```

可以看到，使用安全等于运算符时，两边的操作数的值都为NULL时，返回的结果为1而不是NULL，其他返回结果与等于运算符相同。

**3．不等于运算符**
不等于运算符（<>和!=）用于判断两边的数字、字符串或者表达式的值是否不相等，如果不相等则返回1，相等则返回0。不等于运算符不能判断NULL值。如果两边的值有任意一个为NULL，或两边都为NULL，则结果为NULL。
SQL语句示例如下：

```mysql
mysql> SELECT 1 <> 1, 1 != 2, 'a' != 'b', (3+4) <> (2+6), 'a' != NULL, NULL <> NULL; 
+--------+--------+------------+----------------+-------------+--------------+
| 1 <> 1 | 1 != 2 | 'a' != 'b' | (3+4) <> (2+6) | 'a' != NULL | NULL <> NULL |
+--------+--------+------------+----------------+-------------+--------------+
|      0 |   1    |       1    |            1   |     NULL    |         NULL |
+--------+--------+------------+----------------+-------------+--------------+
1 row in set (0.00 sec)
```

此外，还有非符号类型的运算符：

![非符号类型运算符1](图片/基础/运算符/非符号类型运算符1.png)

![非符号类型运算符2](图片/基础/运算符/非符号类型运算符2.png)

![非符号类型运算符3](图片/基础/运算符/非符号类型运算符3.png)

**4. 空运算符**
空运算符（IS NULL或者ISNULL）判断一个值是否为NULL，如果为NULL则返回1，否则返回0。
SQL语句示例如下：

```mysql
mysql> SELECT NULL IS NULL, ISNULL(NULL), ISNULL('a'), 1 IS NULL;
+--------------+--------------+-------------+-----------+
| NULL IS NULL | ISNULL(NULL) | ISNULL('a') | 1 IS NULL |
+--------------+--------------+-------------+-----------+
|            1 |            1 |           0 |         0 |
+--------------+--------------+-------------+-----------+
1 row in set (0.00 sec)
```

```mysql
#查询commission_pct等于NULL。比较如下的四种写法
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NULL;
SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE ISNULL(commission_pct);
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = NULL;
```

```mysql
SELECT last_name, manager_id
FROM   employees
WHERE  manager_id IS NULL;
```

**5. 非空运算符**
非空运算符（IS NOT NULL）判断一个值是否不为NULL，如果不为NULL则返回1，否则返回0。
SQL语句示例如下：

```mysql
mysql> SELECT NULL IS NOT NULL, 'a' IS NOT NULL,  1 IS NOT NULL; 
+------------------+-----------------+---------------+
| NULL IS NOT NULL | 'a' IS NOT NULL | 1 IS NOT NULL |
+------------------+-----------------+---------------+
|                0 |               1 |             1 |
+------------------+-----------------+---------------+
1 row in set (0.01 sec)
```

```mysql
#查询commission_pct不等于NULL
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NOT NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT ISNULL(commission_pct);
```

**6. 最小值运算符**
语法格式为：LEAST(值1，值2，...，值n)。其中，“值n”表示参数列表中有n个值。在有两个或多个参数的情况下，返回最小值。

```mysql
mysql> SELECT LEAST (1,0,2), LEAST('b','a','c'), LEAST(1,NULL,2);
+---------------+--------------------+-----------------+
| LEAST (1,0,2) | LEAST('b','a','c') | LEAST(1,NULL,2) |
+---------------+--------------------+-----------------+
|       0       |        a           |      NULL       |
+---------------+--------------------+-----------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数是整数或者浮点数时，LEAST将返回其中最小的值；当参数为字符串时，返回字母表中顺序最靠前的字符；当比较值列表中有NULL时，不能判断大小，返回值为NULL。

**7. 最大值运算符**
语法格式为：GREATEST(值1，值2，...，值n)。其中，n表示参数列表中有n个值。当有两个或多个参数时，返回值为最大值。假如任意一个自变量为NULL，则GREATEST()的返回值为NULL。

```mysql
mysql> SELECT GREATEST(1,0,2), GREATEST('b','a','c'), GREATEST(1,NULL,2);
+-----------------+-----------------------+--------------------+
| GREATEST(1,0,2) | GREATEST('b','a','c') | GREATEST(1,NULL,2) |
+-----------------+-----------------------+--------------------+
|               2 | c                     |               NULL |
+-----------------+-----------------------+--------------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数中是整数或者浮点数时，GREATEST将返回其中最大的值；当参数为字符串时，返回字母表中顺序最靠后的字符；当比较值列表中有NULL时，不能判断大小，返回值为NULL。

**8. BETWEEN AND运算符**
BETWEEN运算符使用的格式通常为SELECT D FROM TABLE WHERE C BETWEEN A AND B，此时，当C大于或等于A，并且C小于或等于B时，结果为1，否则结果为0。

```mysql
mysql> SELECT 1 BETWEEN 0 AND 1, 10 BETWEEN 11 AND 12, 'b' BETWEEN 'a' AND 'c';
+-------------------+----------------------+-------------------------+
| 1 BETWEEN 0 AND 1 | 10 BETWEEN 11 AND 12 | 'b' BETWEEN 'a' AND 'c' |
+-------------------+----------------------+-------------------------+
|                 1 |                    0 |                       1 |
+-------------------+----------------------+-------------------------+
1 row in set (0.00 sec)
```

```mysql
SELECT last_name, salary
FROM   employees
WHERE  salary BETWEEN 2500 AND 3500;
```

**9. IN运算符**
IN运算符用于判断给定的值是否是IN列表中的一个值，如果是则返回1，否则返回0。如果给定的值为NULL，或者IN列表中存在NULL，则结果为NULL。

```mysql
mysql> SELECT 'a' IN ('a','b','c'), 1 IN (2,3), NULL IN ('a','b'), 'a' IN ('a', NULL);
+----------------------+------------+-------------------+--------------------+
| 'a' IN ('a','b','c') | 1 IN (2,3) | NULL IN ('a','b') | 'a' IN ('a', NULL) |
+----------------------+------------+-------------------+--------------------+
|            1         |        0   |         NULL      |         1          |
+----------------------+------------+-------------------+--------------------+
1 row in set (0.00 sec)
```

```mysql
SELECT employee_id, last_name, salary, manager_id
FROM   employees
WHERE  manager_id IN (100, 101, 201);
```

**10. NOT IN运算符**
NOT IN运算符用于判断给定的值是否不是IN列表中的一个值，如果不是IN列表中的一个值，则返回1，否则返回0。

```mysql
mysql> SELECT 'a' NOT IN ('a','b','c'), 1 NOT IN (2,3);
+--------------------------+----------------+
| 'a' NOT IN ('a','b','c') | 1 NOT IN (2,3) |
+--------------------------+----------------+
|                 0        |            1   |
+--------------------------+----------------+
1 row in set (0.00 sec)
```

**11. LIKE运算符**
LIKE运算符主要用来匹配字符串，通常用于模糊匹配，如果满足条件则返回1，否则返回0。如果给定的值或者匹配条件为NULL，则返回结果为NULL。

LIKE运算符通常使用如下通配符：

```mysql
“%”：匹配0个或多个字符。
“_”：只能匹配一个字符。
```

SQL语句示例如下：

```mysql
mysql> SELECT NULL LIKE 'abc', 'abc' LIKE NULL;  
+-----------------+-----------------+
| NULL LIKE 'abc' | 'abc' LIKE NULL |
+-----------------+-----------------+
|          NULL   |          NULL   |
+-----------------+-----------------+
1 row in set (0.00 sec)
```

```mysql
SELECT	first_name
FROM 	employees
WHERE	first_name LIKE 'S%';
```

```mysql
SELECT last_name
FROM   employees
WHERE  last_name LIKE '_o%';
```

**ESCAPE**

- 回避特殊符号的：**使用转义符**。例如：将[%]转为[$%]、[]转为[$]，然后再加上[ESCAPE‘$’]即可。

```mysql
SELECT job_id
FROM   jobs
WHERE  job_id LIKE ‘IT\_%‘;
```

- 如果使用\表示转义，要省略ESCAPE。如果不是\，则要加上ESCAPE。


```mysql
SELECT job_id
FROM   jobs
WHERE  job_id LIKE ‘IT$_%‘ escape ‘$‘;
```

**12. REGEXP运算符**

REGEXP运算符用来匹配字符串，语法格式为：`expr REGEXP 匹配条件`。如果expr满足匹配条件，返回1；如果不满足，则返回0。若expr或匹配条件任意一个为NULL，则结果为NULL。

REGEXP运算符在进行匹配时，常用的有下面几种通配符：

```
（1）‘^’匹配以该字符后面的字符开头的字符串。
（2）‘$’匹配以该字符前面的字符结尾的字符串。
（3）‘.’匹配任何一个单字符。
（4）“[...]”匹配在方括号内的任何字符。例如，“[abc]”匹配“a”或“b”或“c”。为了命名字符的范围，使用一个‘-’。“[a-z]”匹配任何字母，而“[0-9]”匹配任何数字。
（5）‘*’匹配零个或多个在它前面的字符。例如，“x*”匹配任何数量的‘x’字符，“[0-9]*”匹配任何数量的数字，而“*”匹配任何数量的任何字符。
```

SQL语句示例如下：

```mysql
mysql> SELECT 'shkstart' REGEXP '^s', 'shkstart' REGEXP 't$', 'shkstart' REGEXP 'hk';
+------------------------+------------------------+-------------------------+
| 'shkstart' REGEXP '^s' | 'shkstart' REGEXP 't$' | 'shkstart' REGEXP 'hk'  |
+------------------------+------------------------+-------------------------+
|                      1 |                      1 |                       1 |
+------------------------+------------------------+-------------------------+
1 row in set (0.01 sec)
```

```mysql
mysql> SELECT 'atguigu' REGEXP 'gu.gu', 'atguigu' REGEXP '[ab]';
+--------------------------+-------------------------+
| 'atguigu' REGEXP 'gu.gu' | 'atguigu' REGEXP '[ab]' |
+--------------------------+-------------------------+
|                        1 |                       1 |
+--------------------------+-------------------------+
1 row in set (0.00 sec)
```

## 3、逻辑运算符

逻辑运算符主要用来判断表达式的真假，在MySQL中，逻辑运算符的返回结果为1、0或者NULL。

MySQL中支持4种逻辑运算符如下：

![逻辑运算符](图片/基础/运算符/逻辑运算符.png)

**1．逻辑非运算符**
逻辑非（NOT或!）运算符表示当给定的值为0时返回1；当给定的值为非0值时返回0；当给定的值为NULL时，返回NULL。

```mysql
mysql> SELECT NOT 1, NOT 0, NOT(1+1), NOT !1, NOT NULL;    
+-------+-------+----------+--------+----------+
| NOT 1 | NOT 0 | NOT(1+1) | NOT !1 | NOT NULL |
+-------+-------+----------+--------+----------+
|     0 |     1 |        0 |      1 |     NULL |
+-------+-------+----------+--------+----------+
1 row in set, 1 warning (0.00 sec)
```

```mysql
SELECT last_name, job_id
FROM   employees
WHERE  job_id NOT IN ('IT_PROG', 'ST_CLERK', 'SA_REP');
```

**2．逻辑与运算符**
逻辑与（AND或&&）运算符是当给定的所有值均为非0值，并且都不为NULL时，返回1；当给定的一个值或者多个值为0时则返回0；否则返回NULL。

```mysql
mysql> SELECT 1 AND -1, 0 AND 1, 0 AND NULL, 1 AND NULL;
+----------+---------+------------+------------+
| 1 AND -1 | 0 AND 1 | 0 AND NULL | 1 AND NULL |
+----------+---------+------------+------------+
|        1 |       0 |          0 |       NULL |
+----------+---------+------------+------------+
1 row in set (0.00 sec)
```

```mysql
SELECT employee_id, last_name, job_id, salary
FROM   employees
WHERE  salary >=10000
AND    job_id LIKE '%MAN%';
```

**3．逻辑或运算符**
逻辑或（OR或||）运算符是当给定的值都不为NULL，并且任何一个值为非0值时，则返回1，否则返回0；当一个值为NULL，并且另一个值为非0值时，返回1，否则返回NULL；当两个值都为NULL时，返回NULL。

```mysql
mysql> SELECT 1 OR -1, 1 OR 0, 1 OR NULL, 0 || NULL, NULL || NULL;     
+---------+--------+-----------+-----------+--------------+
| 1 OR -1 | 1 OR 0 | 1 OR NULL | 0 || NULL | NULL || NULL |
+---------+--------+-----------+-----------+--------------+
|       1 |      1 |         1 |    NULL   |       NULL   |
+---------+--------+-----------+-----------+--------------+
1 row in set, 2 warnings (0.00 sec)
```

```mysql
#查询基本薪资不在9000-12000之间的员工编号和基本薪资
SELECT employee_id,salary FROM employees 
WHERE NOT (salary >= 9000 AND salary <= 12000);

SELECT employee_id,salary FROM employees 
WHERE salary <9000 OR salary > 12000;

SELECT employee_id,salary FROM employees 
WHERE salary NOT BETWEEN 9000 AND 12000;
```

```mysql
SELECT employee_id, last_name, job_id, salary
FROM   employees
WHERE  salary >= 10000
OR     job_id LIKE '%MAN%';
```

> 注意：
>
> OR可以和AND一起使用，但是在使用时要注意两者的优先级，由于AND的优先级高于OR，因此先对AND两边的操作数进行操作，再与OR中的操作数结合。

**4．逻辑异或运算符**
逻辑异或（XOR）运算符是当给定的值中任意一个值为NULL时，则返回NULL；如果两个非NULL的值都是0或者都不等于0时，则返回0；如果一个值为0，另一个值不为0时，则返回1。

```mysql
mysql> SELECT 1 XOR -1, 1 XOR 0, 0 XOR 0, 1 XOR NULL, 1 XOR 1 XOR 1, 0 XOR 0 XOR 0;
+----------+---------+---------+------------+---------------+---------------+
| 1 XOR -1 | 1 XOR 0 | 0 XOR 0 | 1 XOR NULL | 1 XOR 1 XOR 1 | 0 XOR 0 XOR 0 |
+----------+---------+---------+------------+---------------+---------------+
|        0 |       1 |       0 |       NULL |             1 |             0 |
+----------+---------+---------+------------+---------------+---------------+
1 row in set (0.00 sec)
```

```mysql
select last_name,department_id,salary 
from employees
where department_id in (10,20) XOR salary > 8000;
```

## 4、位运算符

位运算符是在二进制数上进行计算的运算符。位运算符会先将操作数变成二进制数，然后进行位运算，最后将计算结果从二进制变回十进制数。

MySQL支持的位运算符如下：

![位运算符](图片/基础/运算符/位运算符.png)

**1．按位与运算符**
按位与（&）运算符将给定值对应的二进制数逐位进行逻辑与运算。当给定值对应的二进制位的数值都为1时，则该位返回1，否则返回0。

```mysql
mysql> SELECT 1 & 10, 20 & 30;
+--------+---------+
| 1 & 10 | 20 & 30 |
+--------+---------+
|      0 |      20 |
+--------+---------+
1 row in set (0.00 sec)
```

1的二进制数为0001，10的二进制数为1010，所以1 & 10的结果为0000，对应的十进制数为0。20的二进制数为10100，30的二进制数为11110，所以20 & 30的结果为10100，对应的十进制数为20。

**2. 按位或运算符**
按位或（|）运算符将给定的值对应的二进制数逐位进行逻辑或运算。当给定值对应的二进制位的数值有一个或两个为1时，则该位返回1，否则返回0。

```mysql
mysql> SELECT 1 | 10, 20 | 30; 
+--------+---------+
| 1 | 10 | 20 | 30 |
+--------+---------+
|     11 |      30 |
+--------+---------+
1 row in set (0.00 sec)
```

1的二进制数为0001，10的二进制数为1010，所以1 | 10的结果为1011，对应的十进制数为11。20的二进制数为10100，30的二进制数为11110，所以20 | 30的结果为11110，对应的十进制数为30。

**3. 按位异或运算符**
按位异或（^）运算符将给定的值对应的二进制数逐位进行逻辑异或运算。当给定值对应的二进制位的数值不同时，则该位返回1，否则返回0。

```mysql
mysql> SELECT 1 ^ 10, 20 ^ 30; 
+--------+---------+
| 1 ^ 10 | 20 ^ 30 |
+--------+---------+
|     11 |      10 |
+--------+---------+
1 row in set (0.00 sec)
```

1的二进制数为0001，10的二进制数为1010，所以1 ^ 10的结果为1011，对应的十进制数为11。20的二进制数为10100，30的二进制数为11110，所以20 ^ 30的结果为01010，对应的十进制数为10。

再举例：

```mysql
mysql> SELECT 12 & 5, 12 | 5,12 ^ 5 FROM DUAL;
+--------+--------+--------+
| 12 & 5 | 12 | 5 | 12 ^ 5 |
+--------+--------+--------+
|      4 |     13 |      9 |
+--------+--------+--------+
1 row in set (0.00 sec)
```

![位运算](图片/基础/运算符/位运算.png)

**4. 按位取反运算符**
按位取反（~）运算符将给定的值的二进制数逐位进行取反操作，即将1变为0，将0变为1。

```mysql
mysql> SELECT 10 & ~1;
+---------+
| 10 & ~1 |
+---------+
|      10 |
+---------+
1 row in set (0.00 sec)
```

由于按位取反（~）运算符的优先级高于按位与（&）运算符的优先级，所以10 & ~1，首先，对数字1进行按位取反操作，结果除了最低位为0，其他位都为1，然后与10进行按位与操作，结果为10。

**5. 按位右移运算符**
按位右移（>>）运算符将给定的值的二进制数的所有位右移指定的位数。右移指定的位数后，右边低位的数值被移出并丢弃，左边高位空出的位置用0补齐。

```mysql
mysql> SELECT 1 >> 2, 4 >> 2;
+--------+--------+
| 1 >> 2 | 4 >> 2 |
+--------+--------+
|      0 |      1 |
+--------+--------+
1 row in set (0.00 sec)
```

1的二进制数为0000 0001，右移2位为0000 0000，对应的十进制数为0。4的二进制数为0000 0100，右移2位为0000 0001，对应的十进制数为1。

**6. 按位左移运算符**
按位左移（<<）运算符将给定的值的二进制数的所有位左移指定的位数。左移指定的位数后，左边高位的数值被移出并丢弃，右边低位空出的位置用0补齐。

```mysql
mysql> SELECT 1 << 2, 4 << 2;  
+--------+--------+
| 1 << 2 | 4 << 2 |
+--------+--------+
|      4 |     16 |
+--------+--------+
1 row in set (0.00 sec)
```

1的二进制数为0000 0001，左移两位为0000 0100，对应的十进制数为4。4的二进制数为0000 0100，左移两位为0001 0000，对应的十进制数为16。

## 5、运算符的优先级

![运算符优先级1](图片/基础/运算符/运算符优先级1.png)

![运算符优先级2](图片/基础/运算符/运算符优先级2.png)

数字编号越大，优先级越高，优先级高的运算符先进行计算。可以看到，赋值运算符的优先级最低，使用“()”括起来的表达式的优先级最高。



## 拓展：使用正则表达式查询

正则表达式通常被用来检索或替换那些符合某个模式的文本内容，根据指定的匹配模式匹配文本中符合要求的特殊字符串。例如，从一个文本文件中提取电话号码，查找一篇文章中重复的单词或者替换用户输入的某些敏感词语等，这些地方都可以使用正则表达式。正则表达式强大而且灵活，可以应用于非常复杂的查询。

MySQL中使用REGEXP关键字指定正则表达式的字符匹配模式。下表列出了REGEXP操作符中常用字符匹配列表。

![正则表达式查询](图片/基础/运算符/正则表达式查询.png)

**1. 查询以特定字符或字符串开头的记录**
字符‘^’匹配以特定字符或者字符串开头的文本。

在fruits表中，查询f_name字段以字母‘b’开头的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^b';
```

**2. 查询以特定字符或字符串结尾的记录**
字符‘$’匹配以特定字符或者字符串结尾的文本。

在fruits表中，查询f_name字段以字母‘y’结尾的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'y$';
```

**3. 用符号"."来替代字符串中的任意一个字符**
字符‘.’匹配任意一个字符。
在fruits表中，查询f_name字段值包含字母‘a’与‘g’且两个字母之间只有一个字母的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'a.g';
```

**4. 使用"*"和"+"来匹配多个字符**
星号‘*’匹配前面的字符任意多次，包括0次。加号‘+’匹配前面的字符至少一次。

在fruits表中，查询f_name字段值以字母‘b’开头且‘b’后面出现字母‘a’的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba*';
```

在fruits表中，查询f_name字段值以字母‘b’开头且‘b’后面出现字母‘a’至少一次的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba+';
```

**5. 匹配指定字符串**
正则表达式可以匹配指定字符串，只要这个字符串在查询文本中即可，如要匹配多个字符串，多个字符串之间使用分隔符‘|’隔开。

在fruits表中，查询f_name字段值包含字符串“on”的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on';
```

在fruits表中，查询f_name字段值包含字符串“on”或者“ap”的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on|ap';
```

之前介绍过，LIKE运算符也可以匹配指定的字符串，但与REGEXP不同，LIKE匹配的字符串如果在文本中间出现，则找不到它，相应的行也不会返回。REGEXP在文本内进行匹配，如果被匹配的字符串在文本中出现，REGEXP将会找到它，相应的行也会被返回。对比结果如下所示。

在fruits表中，使用LIKE运算符查询f_name字段值为“on”的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name like 'on';
Empty set(0.00 sec)
```

**6. 匹配指定字符中的任意一个**
方括号“[]”指定一个字符集合，只匹配其中任何一个字符，即为所查找的文本。

在fruits表中，查找f_name字段中包含字母‘o’或者‘t’的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '[ot]';
```

在fruits表中，查询s_id字段中包含4、5或者6的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE s_id REGEXP '[456]';
```

**7. 匹配指定字符以外的字符**
`“[^字符集合]”`匹配不在指定集合中的任何字符。

在fruits表中，查询f_id字段中包含字母a~e和数字1~2以外字符的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_id REGEXP '[^a-e1-2]';
```

**8. 使用{n,}或者{n,m}来指定字符串连续出现的次数**
“字符串{n,}”表示至少匹配n次前面的字符；“字符串{n,m}”表示匹配前面的字符串不少于n次，不多于m次。例如，a{2,}表示字母a连续出现至少2次，也可以大于2次；a{2,4}表示字母a连续出现最少2次，最多不能超过4次。

在fruits表中，查询f_name字段值出现字母‘x’至少2次的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'x{2,}';
```

在fruits表中，查询f_name字段值出现字符串“ba”最少1次、最多3次的记录，SQL语句如下：

```mysql
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'ba{1,3}';
```
