# Centos6.5-nodejsv4.X-express
Centos6.5+nodejsv4.x+express的安装

很高兴第一次在github中写东西，以后我会多在这里边写东西的
为什么我想要写这个Centos6.5+nodejsv4.x+express的安装呢？首先我接触nodejs在4月份，
然后一直是在windows下使用nodejs+express的，windows我们很熟悉，也容易处理一些文件
等等，但是我们工作的时候避免不了在linux下使用各种软件，这里不得不提到nodejs了，
当然linux的的性能等等的优点我这里就不阐述了。
下面进入正题：
（PS：网上关于Centos6.5+nodejsv4.x+express确实也很多，但是我照着网上的教程搞了一天还是失败了
而且还很麻烦，因为centos里的东西太老了，比如使用nodejs4.x以上就要升级gcc到4.8以上，这个我尝
试了好多还是失败了，后来我差点绝望了，不过我发现了一个办法可以，在这里跟大家说一声，希望少走
弯路）
(注意：这里的所有操作都在root模式下)
1.安装centos6.5可以在虚拟机下安装
2.打开centos6.5，打开终端，在root
模式下操作，root模式稍微说一下（su
回车，然后输入密码即可）
3.获取nodejs 资源，这里有一下几种模式
 #4.x
curl --silent --location https://rpm.nodesource.com/setup_4.x | bash -

# 5.x
curl --silent --location https://rpm.nodesource.com/setup_5.x | bash -

# 0.10
curl --silent --location https://rpm.nodesource.com/setup | bash -
我当然安装比较新的版本，4.X
在root模式下输入其中的一个
4.安装
yum install -y nodejs
5.测试是否成功
node -v
成功会返回版本号
--------------------------------------------------------------------
这样看起来似不似很简单，没错nodejs安装成功了
不过我们要设置一下环境变量，这里使用起来简单
（也很简单哦）

a、切换到 root 用户
b、vi /etc/profile
c、在最下面加入
# node （注释作用）
    export NODE_HOME=/usr/local/src/node-v4.2.3-linux-x86
    export PATH=$PATH:$NODE_HOME/bin  
    export NODE_PATH=$NODE_HOME/lib/node_modules 
d、:wq （保存并退出）
e、source /etc/profile （使配置文件生效）
-------------------------------------------------------------------
下面可以安装express框架，具体express框架的作用自己谷歌一下
1.npm install express -g
不过express安装之后还要安装一下npm install -g express-generator
具体为什么可以自己去了解这里就不多说了
2.验证是否
建立一个文件夹，然后express myblog
然后你们就应该都会了。。。。。。
