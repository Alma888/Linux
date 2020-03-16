# Linux

1、回顾命令：
cd / ls / pwd   路径相关
touch / mkdir /  rm   创建删除文件（包括文件夹）
cp  /  mv                   复制文件 /  剪切文件

man —— manual （说明书）
命令 --help 去查看   不是完整说明 
man 命令                 完整说明书  （按 q 退出，上下键翻动）

2、显示文件内容的命令：
cat —— 显示文件内容
cat   文件名 —— 只显示文件内容
cat -n 文件名  ——直接带行号显示出内容

tac —— 反过来显示文件内容（实际上没啥用）
less —— 显示文件内容，最多只会显示一屏（按 q 退出，上下键翻动）
more —— 显示文件内容，最多只会显示一屏（按 q 退出，只能往下走，按 空
                 格 切换下一屏）
head —— 显示文件内容，只显示前 n 行
eg：head -n 5 cron   意思是只显示cron这个文件的前5行内容（见下图）
 
tail —— 显示文件内容，只显示最后 n 行
eg：tail -n 5 cron   意思是只显示cron这个文件的最后5行内容
vi —— 作为编辑器，肯定也可以，如果文件太大，用vi 会很卡，不建议用 vi


3、习惯上，操作系统中会为每个进程提前打开三个流：流的根源  都是IO(设备)
     输入流：标准输入流：System.in (InputStream)       0
     输出流：标准输出流：System.out (PrintStream)     1
     输出流：标准错误流：System.err (PrintStream)      2


4、输入输出重定向（redirect）（记忆）

5、输出标准错误

6、管道（PIPE）作用 （记忆）

            ————编译运行程序操作————



7、串起来的管道经常考：（记忆）

8、grep —— 过滤出 标准输入中包含某个词的所有行


【学习Linux —— 鸟哥的一本书】

9、显示时间的命令
       date 命令
       date 指定格式显示时间：date +%Y:%m:%d
10、时间戳
11、环境搭建


          开发环境：Windows
          构建环境：Linux  /Windows
          测试环境：Windows
          生产环境：Linux
          代码托管仓库：github


       1、Linux 上的两个 http 客户端 （下面只是下载了安装包，未解压）
        （1）curl   ——http 客户端             curl --version
             curl https://mirror.bit.edu.cn/apache/tomcat/tomcat-  8/v8.5.51/bin/apache-tomcat-
                8.5.51.zip  -o 文件名  
        （2）wget ——http 客户端             wget --version
              wget https://mirror.bit.edu.cn/apache/tomcat/tomcat-  8/v8.5.51/bin/apache-tomcat-
                8.5.51.zip  -O 文件名  
       
       2、通过 yum 安装一个 zip 解压工具（并解压上面的安装包）
              yum install -y unzip
             解压文件：unzip  apache-tomcat-8.5.51.zip

       3、这些所有的命令中：
            有两个必须要一直运行着，其他的临时运行一次就行
            两个 Server： MySQL Server
                                   Tomcat   Server
           上面涉及 Linux 上如何查看进程情况：(两个命令)
             （1）top 命令   ——按 q 退出
             （2）ps aux ——显示所有的进程
                      ps -elf  ——和上面的命令都是用来查看进程的
                      （但是两者都很少单独使用，一般配合grep用）
                         ps aux | grep mysql       ps -elf | grep mysql
             （3）间接方式查看 MySQL 是否正在运行
                      MySQL 是个TCP Server，如果正在运行那么一定监听某个端口
                      通过查看网络情况，来判断 MySQL 是否正在运行
                         A、netstat -nlpt

      4、Linux 的用户和权限管理（重要）      

          （1）权限是什么意思：
                    1. 可读： 是否有看文件内容的权限
                    2. 可写： 是否拥有修改文件内容的权限
                           文件夹的可写权限，决定了你是否可在这个文件夹下创建文件
                    3. 可执行：这个文件是否可以被看做一个程序——是否可以用它
                                      来启动变成一个进程
                            A、如果在PATH 环境变量下， some_command
                            B、如果不在 PATH 环境变量下
                              （1）绝对路径 /root/some_command
                              （2）相对路径 要求必须以 . 或者 .. 开头 ./some_command

