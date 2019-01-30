# maven_study
- maven 是一个项目构建工具，用来依赖管理的。

- struts2-core-2.3.4.jar 
- 公司名称 - 项目名称 - 版本号

- 依赖管理：maven的依赖管理就是找jar包的过程
- 项目构建：项目在编码完成之后 对项目进行编译 测试 打包 部署 等一系列操作都可以通过命令来实现

- 通过maven命令的方式将web发布到Tomcat上
 - 在项目的根目录下执行 mvn tomcat:run

- maven程序是java开发的 它的运行依赖jdk
- 下载maven.jar包  解压
- 配置环境变量 
- MAVEN_HOME  maven的解压路径 当前的bin目录下
- path中添加 %MAVEN_HOME%\bin (注意后面还有一个\bin 而且你jdk的配置一定要使用JAVA_HOME的方式进行配置才可以)
- 验证成功与否用 mvn -v    java -version


- maven仓库类型
- 本地仓库 就在程序员自己的笔记本上
- 私服 存在于局域网内的一台服务器上 
- 中央仓库 在互联网上 存在世界上基本所有的jar

- 配置maven的本地仓库
- 找到解压文件中setting文件  放出其中的localRepository 进行配置 
- 配置的地址就是你本地仓库的地址 
- 你配置完本地仓库之后 如果需要配置远程仓库 可以在m

- maven项目的标准目录结构
pom.xml文件  maven的核心配置文件
src          项目源码
 -main
    -java         你主要的程序
    -resources    配置文件
    -webapp       项目页面素材
 -test
    -java
    -resources
target      项目编译完成后 文件的存放位置


-------------------中间插入一个话题----------------------------
- 把本地项目导入到GitHub上是怎么操作的
- 最简单的方式我直接在本地创建好项目以后 点击idea上的VCS 里面的 import into version control  里面有一个GitHub
- 还有一种方式 先创建GitHub仓库 然后本地创建项目 git 初始化，git remote add origin https://.....
-   git pull --allow-unrelated-histories  应该是类似的功能 
- 基本就是这个样子的
-------------------------------------------------------------
    
- maven的常用命令
- 清理：就是把我编译好的文件进行一个清除,编译好有一个target文件 执行mvn clean后,这个文件就被清除了
- mvn clean
- 编译：就是把我写好的代码进行编译操作 编译好的文件的位置在 target/classes下面
- mvn compile
- 测试：执行test文件夹下的测试类 这个对文件名称有要求 必须叫 xxxTest.java
- mvn test
- 打包：一种就是我直接使用idea上的build进行打包(war/jar) 另一种就是我执行mvn package进行打包
- mvn package
- 安装：可能很多项目都需要你自己写的工具类 这时候你就可以把这个工具类安装到本地项目中了
- mvn install
- 以上就是maven的生命周期 执行下面的命令 上面的都已经执行了 在maven中存在3套声明周期
- cleanLifeCycle: 清理声明周期 mvn clean
- defaultLifeCycle: 默认生命周期 compile test package install deploy
- siteLifeCycle: 站点生命周期 mvn site 
- 不同的生命周期相互不影响,在一套生命周期中，执行后面的命令，前面的操作会自动执行

- maven 整合web项目案例
- 如果是eclipse的话 需要安装maven插件  然后配置一下maven
- 如果是idea 在settings中进行设置 这个看视频发现这个比eclipse要好处理一些 这个其实在创建项目的时候就配置好了

- 如何进行构建索引(为了快速找到jar) setting maven repositories 然后里面就有你之前构建的索引 

