#copy Moose Dojo
#Serpico CBD 1.1
##by helit
渗透测试报告汉化版
对views下面的文件夹进行了汉化
#简单的报告编写和合作工具
Serpico是一个生成渗透测试报告和合作的工具。它是为了减少为编写渗透测试报告花费的时间

演示视频地址
[Serpico - Demo 1](https://www.youtube.com/watch?v=G_qYcL4ynSc)

##安装
Serpico是使用Ruby编写的，用到了sinatra，Bootstrap和haml，安装应该很简单：

- 你需要一个Ruby版本，Rvm是Ruby版本控制工具，需要Ruby2.1.5版本的支持，rvm官网https://rvm.io/rvm/install，如果遇到权限问题，可以使用sudo命令

```
curl -sSL https://get.rvm.io | bash  
rvm install 2.1.5
rvm use 2.1.5
```

- 如果你是在Ubuntu（或者在Kali上验证）上运行的，你将会需要下列依赖

```
apt-get install libsqlite3-dev libxslt-dev libxml2-dev zlib1g-dev gcc
```

- 进入Serpoco 目录然后安装proper gems:

```
cd Serpico
gem install bundler
bundle install 
```

- 第一次需要运行初始化脚本,会初始化管理员密码

```
ruby scripts/first_time.rb
```

- 启动Serpico

```
ruby serpico.rb
```

- 原版问题在管理员登录了几次之后密码失效，所以需要下列脚本来重置密码

```
ruby script/reset_pw.rb
```

注意：首先会产生一个新的证书然后使用它，为额你自己能使用，需要把它用加到root目录里面
打开你的浏览器输入https://127.0.0.1:8443（或者你自己定义的端口） 然后开始使用

##关于Serpico
Serpico核心是报表生成工具，但定位是打造信息安全报告。创建一个报告，用户从模板数据库中添加“findings”（个人理解就是漏洞）到报告里面。当“findings”足够多得实惠，点击“生成报告”就会生成漏洞报告。报告是通过报告模板来设计的，报告模板可以通过web界面来添加；默认会包含一个模板。报告模板是使用通用的Markup Language从web界面截取数据，然后导入到报告里面。

##特点
####报告模板很容易配置
**Philosophy：配置报告模板很简单（不简单啊，学了好半天呢）

####模板数据库

####生成附件

####微软word meta-language 自己看吧
https://github.com/MooseDojo/Serpico/wiki/Serpico-Meta-Language-In-Depth

####插入截图
https://github.com/MooseDojo/Serpico/wiki/Inserting-Screenshots



下面就先不翻译了


# Serpico
## SimplE RePort wrIting and CollaboratiOn tool
Serpico is a penetration testing report generation and collaboration tool. It was developed to cut down on the amount of time it takes to write a penetration testing report.

Video Demo of Functionality:
[Serpico - Demo 1](https://www.youtube.com/watch?v=G_qYcL4ynSc)

## Installation
Serpico is written in Ruby using Sinatra, Bootstrap, and Haml. Installation should be easy:

- You will need a copy of Ruby. RVM is suggested (https://rvm.io/rvm/install). ruby version 2.1.5 is supported.

```
rvm install 2.1.5
rvm use 2.1.5
```

- If you are running Ubuntu (or also verified on Kali) you will need a couple of dependencies:
```
apt-get install libsqlite3-dev libxslt-dev libxml2-dev zlib1g-dev gcc
```

- Go into Serpico and install the proper gems:
```
cd Serpico
gem install bundler
bundle install
```

- Run the first time script to get setup:
```
ruby scripts/first_time.rb
```

To start using Serpico:
```
ruby serpico.rb
```

Note: A new cert is created on first use. To add your own, just add it to the root directory.

Point your browser to https://127.0.0.1:8443 (or whatever port you assigned) to start using.


## About Serpico
Serpico is at its core a report generation tool but targeted at creating information security reports. When building a report the user adds "findings" from the template database to the report. When there are enough findings, click 'Generate Report' to create the docx with your findings. The docx design comes from a Report Template which can be added through the UI; a default one is included. The Report Templates use a custom Markup Language to stub the data from the UI (i.e. findings, customer name, etc) and put them into the report.

## Features
#### Report Template Editing is Easy
**Philosophy: Editing a report template should be easy.**
During peer review we would constantly ran into "little things" we were fixing from the report template; an extra space here, a misspelling there. But it adds up. With Serpico, "fix" the report template, upload it back through the UI, and generate a new report; the error should be fixed permanently.

#### Template Database
**Philosophy: We do not need to write most findings from scratch.**
Most findings have been found in a previous assessment. In Serpico, all authors can pull findings from the template database and add to the report. A user can also 'Upload' a finding they made into the Template Database to share with everyone.

#### Attachment Collaboration
**Philosophy: It should be easy to share files with teammates.**
Use the 'Add Attachment' functionality to store a file (e.g. screenshots, nmap scans) or share with teammates on a pen test. No thumb drive swapping or e-mailing, just log into the UI and download the files. At the end of the assessment everything traded or generated for that assessment is in one place.


## Microsoft Word Meta-Language
The Meta language used for Microsoft Word was designed to be as simple as possible while still serving enough features to create a basic penetration test report.  That being said it has a learning curve (and many bugs) and I _highly_ suggest looking at "Serpico - Report.docx" or "Serpico - No DREAD.docx" and editing these rather than working from scratch.

Inserting Screenshots
https://github.com/MooseDojo/Serpico/wiki/Inserting-Screenshots

This is an area we know needs development so e-mail me with any ideas.

See the Wiki for more information, [Serpico Meta-Language In Depth](https://github.com/MooseDojo/Serpico/wiki/Serpico-Meta-Language-In-Depth)

## GOTCHAS
- Microsoft has a really annoying habit of changing a character for you. Always beware of this when working with the meta language

## Huge Thanks
* Wouldn't exist without testing, support, and feature suggestion of the rest of the [Moosedojo team!](https://github.com/MooseDojo).
* @d4rkd0s for the great logo work. Thanks!
