## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/kookwe/learn/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
1、请简单介绍一下你所了解的电商行业，常见商业模式，技术特点
中国的电子商务快速发展，交易额连创新高，电子商务在各领域的应用不断拓 
展和深化、相关服务业蓬勃发展、支撑体系不断健全完善、创新的动力和能力 不断增强。 
电子商务正在与实体经济深度融合，进入规模性发展阶段，对经济社会生活的影响不断增大， 
正成为我国经济发展的新引擎。
2、你之前做过电商系统吗？有哪些平台?
优乐选网上商城
主要分为网站前台、运营商后台、商家管理后台三个子系统

3、什么是SOA？
SOA 是 Service-Oriented Architecture 的首字母简称，它是一种支持面向服务的架构样式。 
从服务、基于服务开发和服务的结果来看，面向服务是一种思考方式。其实 SOA 架构更多 
应用于互联网项目开发。
4、Dubbo使用过吗？介绍一下Dubbo的核心原理。
Dubbo 是一个分布式服务框架，是阿里巴巴开源项目。Dubbo 致力于提供高性能和透明化的 RPC 远程服务调用方案，以及 SOA 服务治理方案。


节点角色说明： 
Provider: 暴露服务的服务提供方。 
Consumer: 调用远程服务的服务消费方。 
Registry: 服务注册与发现的注册中心。 
Monitor: 统计服务的调用次调和调用时间的监控中心。 
Container: 服务运行容器。 
调用关系说明： 
0. 服务容器负责启动，加载，运行服务提供者。 
1. 服务提供者在启动时，向注册中心注册自己提供的服务。 
2. 服务消费者在启动时，向注册中心订阅自己所需的服务。 
3. 注册中心返回服务提供者地址列表给消费者，如果有变更，注册中心将基于长连接推 
送变更数据给消费者。 
4. 服务消费者，从提供者地址列表中，基于软负载均衡算法，选一台提供者进行调用， 
如果调用失败，再选另一台调用。 
5. 服务消费者和提供者，在内存中累计调用次数和调用时间，定时每分钟发送一次统计 
数据到监控中心。
5、优乐选商城昨天开发了哪些模块，介绍一下这几个模块的作用？
工程说明： 
Youlexuan_parent 聚合工程 
Youlexuan_pojo 通用实体类层 
youlexuan_dao 通用数据访问层 
youlexuan_xxxxx_interface 某服务层接口 
youlexuan_xxxxx_service 某服务层实现 
youlexuan_xxxxx_web 某 web 工程

6、Zookeeper注册中心
注册中心负责服务地址的注册与查找，相当于目录服务，服务提供者和消费者只在启动时与注册中心交互，注册中心不转发请求，压力较小。

安装zookeeper的步骤


1、确认linux服务器已经安装配置好java环境

java -version


2、配置java环境

  （1）、上传jdk安装包 jdk-8u131-linux-x64.tar.gz


   (2)、解压缩jdk的安装包

   tar xvf jdk-8u131-linux-x64.tar.gz -C /usr/local/



   //注释：  -C  指定文件解压缩目录


 （3）、进入到解压缩目录


   cd /usr/local


 (4)、修改jdk解压缩目录名称

  mv jdk1.8.0_131/ jdk


 （5）、修改linux环境配置文件，配置java环境

   JAVA_HOME   指向java安装目录

   CLASSPATH   指向java的lib


   PATH    指向命令所在目录 bin

   

   vi /etc/profile


   在最后行新增


   #java run time seting

export JAVA_HOME=/usr/local/jdk

export CLASSPATH=$JAVA_HOME/lib

export PATH=$JAVA_HOME/bin:$PATH


  （6）、重新加载配置文件

   source /etc/profile



3、上传zookeeper的安装包到linux服务器


zookeeper-3.4.6.tar.gz


4、解压缩zookeeper的安装包


tar xvf zookeeper-3.4.6.tar.gz -C /usr/local/


5、进入zookeeper安装目录目录


 
cd   /usr/local/zookeeper-3.4.6



6、创建配置文件


   cd  conf


   cp zoo_sample.cfg zoo.cfg


7、启动zookeeper


   cd /usr/local/zookeeper-3.4.6/bin


   ./zkServer.sh start


8、验证zookeeper是否成功启动


  ps -ef|grep zoo


  查看端口是否监听 2181


  netstat -antp|grep 2181
-bash: netstat: command not found      //如果提示命令未找到  需要安装   yum install net-tools -y



[root@bogon bin]# netstat -antp|grep 2181
tcp6       0      0 :::2181                 :::*                    LISTEN      1249/java 


9、启动失败解决方案


   （1）、查看主机名称

     hostname


   (2)、查看主机host主机名称ip地址配置文件


    vi /etc/hosts


    增加ip和主机名称对应条目

    127.0.0.1   bogon

  （3）、重启虚拟机

    reboot


10、打开zookeeper监听端口2181的防火墙


 firewall-cmd --add-port=2181/tcp --permanent

 firewall-cmd --reload


 firewall-cmd --list-all


  


1、AngularJS四大特征？
MVC模式、模块化、自动化双向数据绑定、依赖注入



2、常用的AngularJS指令有哪些？



3、请描述一下基于AngularJS开发的应用，前后端如何进行数据交互。



4、昨天创建了2个封装类，分别作用是什么？
第九天
1、solr是做什么的？核心技术原理？
Apache Solr 是一个流行的开源搜索服务器，它通过使用类似 REST 的 HTTP API，确保你能从几乎任何编程语言来使用 solr。Solr 是一个开源搜索平台，用于构建搜索应用程序。 它建立在 Lucene(全文搜索引擎) 之上。Solr 是企业级的，快速的，高度可扩展的。 
Solr 是一个可扩展的，可部署，搜索/存储引擎，优化搜索大量以文本为中心的数据。 

2、如何配置solr中文分词？
使用IK Analyzer，IK Analyzer 是一个开源的，基于 java 语言开发的轻量级的中文分词工具包。

1、下载 IKAnalyzer for solr5 的源码包，然后使用 Maven 编译，
得到一个文件 IKAnalyzer-5.0.jar 
https://github.com/xuexi007/ik-analyzer-solr5 
2、上传 ik jar 包到/usr/local/solr/server/solr-webapp/webapp/WEB-INF/lib 目录中 
3、修改/usr/local/solr/server/solr/collection1/conf/managed-schema，
添加 fieldType 内容： 
<fieldType name="text_ik" class="solr.TextField"> 
    <analyzer type="index" useSmart="false" 
    class="org.wltea.analyzer.lucene.IKAnalyzer"/> 
    <analyzer type="query" useSmart="true" 
    class="org.wltea.analyzer.lucene.IKAnalyzer"/> 
</fieldType> 
然后，重启 solr



3、solr域有几种类型？有哪些配置选项

复制域：复制域的作用在于将某一个 Field 中的数据复制到另一个域中。
动态域：需要动态扩充字段时，就需要使用动态域。对于优乐选，规格的值是不确定的， 所以我们需要使用动态域来实现

name：指定域的名称 
type：指定域的类型 
indexed：是否索引 
stored：是否存储 
required：是否必须
multiValued：是否多值




4、使用SpringDataSolr操作 solr，如何定义实体bean和域字段的对应关系？
属性使用@Field 注解标识 。 如果属性与 solr 配置文件定义的域名称不一致，需要在注解中指定域名称。如：

@Field 
private Long id; 
@Field("item_title") 
private String title; 
@Field("item_price") 
private BigDecimal price;



5、SpringDataSolr分页查询关键技术点、SpringDataSolr条件查询关键技术点
分页：开始索引、每页记录数
@Test 
public void testPageQuery() { 
Query query = new SimpleQuery("*:*"); 
query.setOffset(10);// 开始索引（默认0） 
query.setRows(20); // 每页记录数(默认10) 
ScoredPage<TbItem> page = solrTemplate.queryForPage(query, TbItem.class); 
System.out.println("总记录数：" + page.getTotalElements()); 
List<TbItem> list = page.getContent(); 
for (TbItem item : list) {
System.out.println(item.getTitle() + item.getPrice()); 
} 
} 


条件查询：criteria

Criteria criteria = new Criteria("item_title").contains("2"); 
criteria = criteria.and("item_price").greaterThan(2020); 
query.addCriteria(criteria); 
Sort s = new Sort(Direction.DESC, "item_price"); 
query.addSort(s);




6、昨天开发的基于solr的商品搜索基本流程
将商品数据先导入到solr中，搜索时从solr库中搜索，根据关键字分页查询
第十天
1、什么是高亮？solr搜索引擎如何使用高亮？
将用户输入的关键字在标题中以红色的字体显示出来，就是搜索中常用的高亮显示
创建高亮查询器对象，根据条件设置需要高亮字段及前后置，发出高亮查询请求，
得到结果后将结果进行遍历，然后将标题替换为高亮的结果
2、请描述一下商品搜索模块的业务规则？
（1）当用户输入关键字搜索后，除了显示列表结果外，还应该显示通过这个关键字搜索到 
的记录都有哪些商品分类。 
（2）根据第一个商品分类查询对应的模板，根据模板查询出品牌列表
（3）根据第一个商品分类查询对应的模板，根据模板查询出规格列表 
（4）当用户点击搜索面板的商品分类时，显示按照这个关键字查询结果的基础上，筛选此 
分类的结果。 
（5）当用户点击搜索面板的品牌时，显示在以上结果的基础上，筛选此品牌的结果 
（6）当用户点击搜索面板的规格时，显示在以上结果的基础上，筛选此规格的结果 
（7）当用户点击价格区间时，显示在以上结果的基础上，按价格进行筛选的结果 
（8）当用户点击搜索面板的相应条件时，隐藏已点击的条件。
3、根据搜索条件获取商品分类如何实现？
（1）搜索面板的商品分类需要使用 Spring Data Solr 的分组查询来实现 
（2）为了能够提高查询速度，我们需要把查询面板的品牌、规格数据提前放入 redis 
（3）查询条件的构建、面板的隐藏需要使用 angularJS 来实现 
（4）后端的分类、品牌、规格、价格区间查询需要使用过滤查询来实现
4、在搜索模块中涉及到品牌和规格数据，在什么地方对品牌和规格数据进行缓存？



5、搜索条件构建的步骤?


6、solr过滤条件如何设置？













### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/kookwe/learn/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
