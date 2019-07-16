



# 安装与环境

## 正常安装，选择电脑位数版本

![1542101250062](https://raw.githubusercontent.com/cwayer/assets/master/1542101250062.png)

## 首次不导入设置

![1542101286857](https://raw.githubusercontent.com/cwayer/assets/master/1542101286857.png)

## 创建工程设置sdk

选择 Create New Project,点击 new 按钮，配置安装的 JDK版本,选择 JDK目录，点击确定

![1542101318857](https://raw.githubusercontent.com/cwayer/assets/master/1542101318857.png)

![1542101354382](https://raw.githubusercontent.com/cwayer/assets/master/1542101354382.png)

一直下一步，创建项目名

![1542101387330](https://raw.githubusercontent.com/cwayer/assets/master/1542101387330.png)

 IDEA的工作界面，我们的项目已经创建好了，如果再新建项目，点击 File->new->Project

![1542101427304](https://raw.githubusercontent.com/cwayer/assets/master/1542101427304.png)

## 字体设置

点击菜单栏上的 File->Settings->Editor->Font 修改字体。

![1542101487665](https://raw.githubusercontent.com/cwayer/assets/master/1542101487665.png)

![1542101504520](https://raw.githubusercontent.com/cwayer/assets/master/1542101504520.png)

## 项目目录

.idea 目录和 demo.iml 和我们开发无关，是IDEA工具自己使用的
out 目录是存储编译后的.class文件
src 目录是存储我们编写的.java源文件

## Maven配置

设置maven仓库

![img](https://raw.githubusercontent.com/cwayer/assets/master/1528254377666.png)

## 其他配置

### 配置编码

![img](https://raw.githubusercontent.com/cwayer/assets/master/1528254443992.png)

### 配置jdk

![img](https://raw.githubusercontent.com/cwayer/assets/master/1528254563988.png)

### 配置快捷键

可以选择模板，自定义请先copy个副本
![img](https://raw.githubusercontent.com/cwayer/assets/master/1529678575704.png)

### 设置idea导入包

（多个同名的类调用不同的包，必须自己手动Alt+Enter设置）
![img](https://raw.githubusercontent.com/cwayer/assets/master/1529678703317.png)

### 自定义自己代码模板

![img](https://raw.githubusercontent.com/cwayer/assets/master/1529678805624.png)

### 提示忽略大小写

默认idea设置是区分大小写的，可以设置关闭

![img](https://raw.githubusercontent.com/cwayer/assets/master/1529679037573.png)

### 配置虚拟机内存

```
修改idea64.exe.vmoptions（64位电脑选择此文件）
一个例子，电脑内存8G，设置如下：
-Xms1024m
-Xmx4096m
-XX:MaxPermSize=1024m
-XX:ReservedCodeCacheSize=1024m
```

### 设置配置编码问题

修改idea64.exe.vmoptions

```
-Dfile.encoding=UTF8
```

# IDEA常用快捷键

```
快捷键 功能
Alt+Enter 导入包，自动修正代码
Ctrl+Y 删除光标所在行
Ctrl+D 复制光标所在行的内容，插入光标位置下面
Ctrl+Alt+L 格式化代码
Ctrl+/ 单行注释
Ctrl+Shift+/ 选中代码注释，多行注释，再按取消注释
Alt+Ins 自动生成代码，toString，get，set等方法
Alt+Shift+上下箭头 移动当前代码行
Ctrl+空格	补全代码
```

## 自定义设置快捷键

部分快捷键冲突，例如Ctrl+空格，因此需要手动修改

`File->Settings->keymap->Main menu->code->Completion->Basic`

![1542101683853](https://raw.githubusercontent.com/cwayer/assets/master/1542101683853.png)

双击 Basic->remove->Ctrl+空格
再次双击 Basic->Add Keyboard->键入 Alt+/->点击OK

