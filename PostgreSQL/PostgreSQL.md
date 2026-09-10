# 一、概述

## 1、数据库

- 数据库是一个结构化的数据集合，能够高效的存储、检索和管理数据
- 数据库不是将数据存储在分散的文件中，而是作为一个中央存储库，应用程序可以以结构化的方式存储和访问信息
- 通俗来讲：即存储数据的 “仓库”，它保存了一系列有组织的数据

















# 二、安装

## 1、windows安装

- 下载地址：https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- 选择对应的安装包
- 双击下载安装包，开始安装













## 2、linux安装

- 1、下载安装包

  - 下载地址：https://ftp.postgresql.org/pub/source/

  - 官网下载地址：https://www.postgresql.org/download/


- 2、将下载好的：postgresql-17.11.tar.gz 上传到 /usr/local 文件夹下解压，并安装编译所需的依赖包

~~~bash
# 进入到存放安装包的目录下
cd /usr/local/

# 解压安装包
tar -zxvf postgresql-17.11.tar.gz

# 安装C/c++编译依赖
yum install gcc gcc-c++ make libicu-devel bison flex readline-devel zlib-devel
~~~

- 3、编译安装

~~~bash
# 进入到解压后的目录里
cd postgresql-17.11/

# 1.配置，指定安装路径，检查编译依赖（前置检查工作）
./configure --prefix=/usr/local/pgsql

# 2.编译（耗时比较久）
make

# 3.安装到 --prefix 指定目录
make install
~~~

- 4、**添加数据库用户，并创建数据存储目录**

~~~bash
# 添加数据库用户
useradd postgres

# 创建数据库存储目录
mkdir /usr/local/pgsql/data

# 把 pg 的数据目录归属改成 postgres 用户、postgres 用户组
chown postgres:postgres /usr/local/pgsql/data
~~~

- 5、**配置环境变量**，编辑  <font color="red">**vim /etc/profile.d/pgsql.sh**</font>，保存后输入：<font color="red">**source /etc/profile.d/pgsql.sh**</font> 生效

~~~bash
# pg 程序安装根目录
export PGHOME=/usr/local/pgsql
# 默认数据目录
export PGDATA=/usr/local/pgsql/data
# 把 pg 的 bin 目录（psql、pg_ctl、initdb 等命令）加到系统 PATH 最前面
export PATH=$PGHOME/bin:$PATH



## 判断是否生效，不带全路径
[root@VM-0-8-centos ~]# psql --version
psql (PostgreSQL) 17.11
~~~

- 6、**系统参数优化**（需要看服务器内存大小，慎重玩）

~~~bash
vim /etc/sysctl.conf

#添加以下内容
vm.nr_hugepages = 6144

#使用参数生效
sysctl -p


## 这一行：**配置 Linux 大页内存（HugePage），预分配 6144 个大页**
Linux 默认大页大小：`2MB`，6144 × 2MB = **12GB 大页内存**

## 什么是 HugePage（大页）
CPU 访问内存时，需要页表做地址转换。默认内存页是 4KB，内存越大，页表就越大，CPU 查找开销高。
HugePage 使用更大的内存页（2MB/1GB），减少页表数量，降低 CPU 开销，**数据库（PostgreSQL、MySQL）强烈推荐开启**，提升性能、减少内存碎片。
vm.nr_hugepages=6144：系统开机预先预留 6144 个 2MB 大页，这部分内存**不会被其他程序抢占**，专门留给 PG 使用

## 查看当前系统大页状态
cat /proc/meminfo | grep Huge
字段说明：0
- `HugePages_Total`：总大页数量（就是你设置的 6144）
- `HugePages_Free`：空闲大页
- `HugePages_Rsvd`：已经被程序预约占用的大页（PG 启动后这里会有数值）

# 注意事项
1. **内存预留**：设置 6144=12G，这部分内存开机就锁死，不能给别的进程。服务器物理内存必须大于 12G，否则系统启动失败！
2. **计算规则**
   - 2MB 大页：页数 = 想要预留内存 (GB) × 512
   - 例：想要预留 8G → 8 ×512=4096；12G →6144；16G →8192
3. **必须在 PG 启动前配置大页**，PG 启动时才会去申请大页；PG 运行中修改不会自动使用。
4. 如果只是测试环境，不想配置大页，可以在 postgresql.conf 设置 `huge_pages = try`，尝试使用大页，失败也可以正常启动。生产环境建议 `huge_pages = on`
5. 开启大页后，**swap 交换分区尽量关闭**，数据库不建议换出到 swap。
~~~

- 7、数据库初始化

~~~bash
#切换到postgres用户
su - postgres

#执行数据初始化
/usr/local/pgsql/bin/initdb -D /usr/local/pgsql/data

#退出postgres用户
exit
~~~

- 8、**修改配置文件**

~~~bash
vim /usr/local/pgsql/data/postgresql.conf

#修改以下配置
listen_addresses = '*'
max_connections = 300
shared_buffers = 4GB
work_mem = 64MB
maintenance_work_mem = 1GB
effective_cache_size = 12GB
wal_buffers = 16MB
checkpoint_completion_target = 0.9


# 参数说明
1、listen_addresses：监听地址，默认使用localhost，使用’*'表示所有
2、max_connections：决定允许的最大数据库连接数。过多的连接会增加系统开销和资源竞争。通常可以使用连接池工具（如PgBouncer）来控制并发连接数；
3、shared_buffers：这是PostgreSQL用于缓存表数据的共享内存区域，通常建议设置为物理内存的25%-40%。如果设置过低，会导致频繁的磁盘访问；设置过高则会占用操作系统内存，减少可用的文件缓存；
4、work_mem：每个查询操作（如排序、哈希表）所使用的内存。这个参数是每个查询连接单独分配的，因此需要根据查询复杂度和并发量合理设置。如果过小，查询需要频繁进行磁盘交换；过大会导致内存不足。典型值在10MB-100MB之间；
5、maintenance_work_mem：控制PostgreSQL在执行维护操作时使用的内存大小，比如创建索引、VACUUM。推荐设置为较大的值，尤其是在大规模数据集上操作时；
6、effective_cache_size：PostgreSQL根据此参数判断系统可用的文件系统缓存大小，从而决定是否使用索引扫描或全表扫描。建议设置为物理内存的50%-75%；
7、wal_buffers：建议设置为shared_buffers的1/32，用于缓冲WAL数据，避免频繁写入磁盘；
8、checkpoint_completion_target：设置为接近1的值可以平滑WAL日志写入压力，减少突发I/O操作
~~~

- 9、**启动服务**

~~~bash
# 9.1 使用自带脚本方式启动
#使用root用户执行以下命令
#复制源码包里的脚本至etc/init.d目录下，并加执行权限
cd /usr/local/postgresql-17.11/ 
cp ./contrib/start-scripts/linux /etc/init.d/postgresql
chmod +x /etc/init.d/postgresql

#启动服务
service postgresql start

#设置开机启动
chkconfig --add postgresql





# 9.2 使用systemd进行管理
vim /etc/systemd/system/postgresql.service

[Unit]
Description=PostgreSQL database server
Documentation=man:postgres(1)
After=network-online.target

[Service]
Type=forking
User=postgres
Group=postgres
Environment=PGDATA=/usr/local/pgsql/data
ExecStart=/usr/local/pgsql/bin/pg_ctl start -D ${PGDATA}
ExecStop=/usr/local/pgsql/bin/pg_ctl stop -D ${PGDATA} -m fast
ExecReload=/home/postgres/bin/pg_ctl reload -D ${PGDATA}
TimeoutSec=300s

[Install]
WantedBy=multi-user.target

# 重新加载
systemctl daemon-reload
systemctl start postgresql
# 注意：如果使用Type=notify要求服务器配置时使用./configure --with-systemd构建






# 9.3 直接使用命令行
su - postgres
/usr/local/pgsql/bin/pg_ctl start -l logfile -D /usr/local/pgsql/data
~~~

- 10、**配置远程访问权限**

~~~bash
vim /usr/local/pgsql/data/pg_hba.conf
#添加以下内容
# 任意 IP，可以用任何数据库账号 + 正确密码登录 PG
host    all             all             0.0.0.0/0               scram-sha-256
# 所有 IP，使用 postgres 用户访问任何库，全部拒绝
host    all             postgres        0.0.0.0/0               reject
# 允许**任意 IP**通过 TCP 连接，访问任意数据库、任意用户，使用`password`认证方式
host    all             all             0.0.0.0/0               password

#然后重启数据库
service postgresql restart
~~~

- `password`：客户端把**明文密码**发给 PostgreSQL 做校验，不安全！ PG17 默认用户密码存储格式是 `scram-sha-256`，**不推荐使用 password 认证**

| 配置项          | 说明                                 | 是否推荐 PG17     |
| --------------- | ------------------------------------ | ----------------- |
| `password`      | 明文传输密码，抓包可拿到密码         | ❌ 不推荐          |
| `scram-sha-256` | 挑战应答加密，密码不会明文在网络传输 | ✅ PG17 默认，推荐 |

- 11、**登录数据库**

~~~bash
#切换到postgres用户
su - postgres
psql

#或在root用户下使用以下命令
psql -U postgres
~~~

- 12、**查看当前登录用户/数据库**

~~~bash
postgres=# \c
You are now connected to database "postgres" as user "postgres".

postgres=# select user;
   user   
----------
 postgres
(1 row)

postgres=# select current_user;
 current_user 
--------------
 postgres
(1 row)

postgres=# select current_database();
 current_database 
------------------
 postgres
(1 row)
~~~

- 13、修改密码

~~~bash
# 切换到postgres系统用户
su - postgres
# 进入psql控制台
psql
# 修改密码
ALTER USER postgres WITH PASSWORD 'li998813';
# 退出后重新登录
\q
~~~

















https://blog.csdn.net/u010100623/article/details/146599345
