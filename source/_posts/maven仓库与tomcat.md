---
title: Maven 软件的安装
date: 2019-07-12 22:29:09
tags:
---

# Maven 软件的安装

Apache-maven-3.5.2 下载地址：http://archive.apache.org/dist/maven/maven-3/

Maven 下载后，将 Maven 解压到一个没有中文没有空格的路径下，比如 D:\software\maven 下面。
解压后目录结构如下：

```
bin:存放了 maven 的命令，比如我们前面用到的 mvn tomcat:run
boot:存放了一些 maven 本身的引导程序，如类加载器等
conf:存放了 maven 的一些配置文件，如 setting.xml 文件
lib:存放了 maven 本身运行所需的一些 jar 包
至此我们的 maven 软件就可以使用了，前提是你的电脑上之前已经安装并配置好了 JDK。
```

## Maven 及 JDK 配置

配置 MAVEN_HOME ，变量值就是你的 maven 安装 的路径（bin 目录之前一级目录）

![1542103258044](https://raw.githubusercontent.com/cwayer/assets/master/1542103258044.png)

同时不要忘记在Path中添加环境变量

```
%MAVEN_HOME%\bin
```

## Maven 软件版本测试

通过命令行 mvn -v命令检查 maven 是否安装成功，看到 maven 的版本为 3.5.2 及 java 版本为 1.8 即为安装成功。

## Maven 仓库的分类

```
本地仓库 ：用来存储从远程仓库或中央仓库下载的插件和 jar 包，项目使用一些插件或 jar 包，
优先从本地仓库查找
默认本地仓库位置在 ${user.dir}/.m2/repository，${user.dir}表示 windows 用户目录。

远程仓库：如果本地需要插件或者 jar 包，本地仓库没有，默认去远程仓库下载。
远程仓库可以在互联网内也可以在局域网内。

中央仓库 ：在 maven 软件中内置一个远程仓库地址 http://repo1.maven.org/maven2 ，它是中央仓库，服务于整个互联网，它是由 Maven 团队自己维护，里面存储了非常全的 jar 包，它包
含了世界上大部分流行的开源项目构件
```

### Maven 本地仓库的配置

将已下载本地仓库 “repository.rar”解压至自己的电脑上，我们解压在 D:\repository 目录下（可以放在没有中文及空格的目录下）。

在 MAVE_HOME/conf/settings.xml 文件中配置本地仓库位置（maven 的安装目录下）
打开 settings.xml文件，配置如下：

![1542104112703](https://raw.githubusercontent.com/cwayer/assets/master/1542104112703.png)

### 全局 setting 与用户 setting

maven 仓库地址、私服等配置信息需要在 setting.xml 文件中配置，分为全局配置和用户配置。
在 maven 安装目录下的有 **conf/setting.xml** 文件，此 setting.xml 文件用于 maven 的所有 project
项目，它作为 maven 的全局配置。
如需要个性配置则需要在用户配置中设置，用户配置的 setting.xml 文件默认的位置在：**${user.dir}** 
**/.m2/settings.xml** 目录中,${user.dir} 指 windows 中的用户目录。
maven 会先找用户配置，如果找到则以用户配置文件为准，否则使用全局配置文件

# idea 的 maven 配置

打开File>Settings 配置 maven
选择本地 maven 安装目录，指定 maven 安装目录下 conf 文件夹中 settings 配置文件。

![1542104333475](https://raw.githubusercontent.com/cwayer/assets/master/1542104333475.png)

创建项目时这些不用改

![1542104391221](https://raw.githubusercontent.com/cwayer/assets/master/1542104391221.png)

## 坐标的来源方式

从互联网搜索
http://search.maven.org/
http://mvnrepository.com/

### 依赖范围

compile：编译范围，指 A 在编译时依赖 B，此范围为默认依赖范围。编译范围的依赖会用在
编译、测试、运行，由于运行时需要所以编译范围的依赖会被打包。
 provided：provided 依赖只有在当 JDK 或者一个容器已提供该依赖之后才使用， provided 依
赖在编译和测试时需要，在运行时不需要，比如：servlet api 被 tomcat 容器提供。
 runtime：runtime 依赖在运行和测试系统的时候需要，但在编译的时候不需要。比如：jdbc
的驱动包。由于运行时需要所以 runtime 范围的依赖会被打包。
 test：test 范围依赖 在编译和运行时都不需要，它们只有在测试编译和测试运行阶段可用，
比如：junit。由于运行时不需要所以 test范围依赖不会被打包。

 system：system 范围依赖与 provided 类似，但是你必须显式的提供一个对于本地系统中 JAR
文件的路径，需要指定 systemPath 磁盘路径，system依赖不推荐使用。

![1542104499125](https://raw.githubusercontent.com/cwayer/assets/master/1542104499125.png)

# TOMCAT

解压即可使用，配置文件在D:\apache-tomcat\apache-tomcat-8.5.31\conf中