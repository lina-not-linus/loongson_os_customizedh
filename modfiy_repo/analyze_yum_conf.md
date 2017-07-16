### 一. yum的主配置文件

指向仓库的位置以及相关的各种配置信息，每一个yum命令可以指向多个仓库，仓库间可以进行优先级的相关配置等，
优先级是由开销决定。

配置文件一般分为两部分组成：主配置文件和各仓库的配置文件。因为如果所有的信息都放在一个文件里那可就变得
太臃肿。其中主配置文件的路径地址在"/etc/yum.conf"，它为各仓库提供公共配置文件；各仓库的配置文件的路径地址
为"/etc/yum.repos.d/*.repo"，里面都是以赋值的格式存在。

### 二. yum主配置文件结构分析：yum.conf
```
[main]        #所有仓库的公共配置

cachedir=/var/cache/yum/$basearch/$releasevar       #缓存目录

keepcache=0       #"keepcache"变量是：程序包在安装后是否保存在缓存中，０是不保存，１是保存

debuglevel=2        #程序安装时的输出信息，数字越大输出信息越多。在生产环境中关闭最好；但在开启
                    #但是开启可以让我们快速定位安装中出现问题的所在。
                    
logfile=/var/log/yum.log        #日志文件

exactarch=1       #安装程序的版本和当前平台保持一致



```
