# 一个企业级电商项目

> 作者：codingLixh

- 时间：2018年2月24号

## 项目介绍：
    
- **工具及环境**：

        jdk_1.8,    IDEA2017,   Maven,  Git,    Github,    windows
        
- **使用框架**：

        Spring SpringMVC Mybatis
        
- **项目结构**：

        项目初始化
           
        用户模块
            
        分类模块
            
        商品模块
            
        购物车模块
           
        收货地址模块
          
        支付模块
            
        订单模块
            
        云服务发布
           
        总结
        
## Coding
    
### 项目初始化

> 创建Maven项目 项目名称：ShoppingTB

- 创建README.md文件  **$ touch README.md**

- 创建.gitignore文件  **$ touch .gitgnore**

- 编辑.gitignore文件(忽略上传的文件)

        *.class
        
        #package file
        *.war
        *.ear
        
        #kdiff3 ignore
        *.orig
        
        #maven ignore
        target/
        
        #eclipse ignore
        .settings/
        .project
        .classpatch
        
        #idea
        .idea/
        /idea/
        *.ipr
        *.iml
        *.iws
        
        #temp file
        *.log
        *.cache
        *.diff
        *.patch
        *.tmp
        
        #system ignore
        .DS_Store
        Thumbs.db

- 项目中安装Git    **$ git init**

- 将项目提交到github
    
    1.   git add .
    2.   git commit -m "初始化项目"
    3.   git remote add origin (github项目地址)
    4.   git push -u origin master
    
> git 的其他命令： 

首次提交 **$ git push -u -f origin master**

创建分支 **$ git checkout -b v1.0 origin/master**

查看分支 **$ git branch**

提交分支 **$ git push origin HEAD -u**

-配置Maven的pom.xml

        <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
            <modelVersion>4.0.0</modelVersion>
            <groupId>cn.codinglixh</groupId>
            <artifactId>ShoppingTB</artifactId>
            <packaging>war</packaging>
            <version>1.0-SNAPSHOT</version>
            <name>ShoppingTB Maven Webapp</name>
            <url>http://maven.apache.org</url>
        
            <!--  设置版本及格式    -->
            <properties>
                <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
                <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
                <maven.compiler.encoding>UTF-8</maven.compiler.encoding>
        
                <org.springframework.version>4.0.0.RELEASE</org.springframework.version>
                <org.mybatis.version>3.4.1</org.mybatis.version>
                <org.mybatis.spring.version>1.3.0</org.mybatis.spring.version>
            </properties>
        
            <dependencies>
        
                <dependency>
                    <groupId>org.apache.tomcat</groupId>
                    <artifactId>tomcat-servlet-api</artifactId>
                    <version>7.0.64</version>
                </dependency>
        
                <dependency>
                    <groupId>org.springframework</groupId>
                    <artifactId>spring-webmvc</artifactId>
                    <version>${org.springframework.version}</version>
                </dependency>
        
                <dependency>
                    <groupId>org.springframework</groupId>
                    <artifactId>spring-oxm</artifactId>
                    <version>${org.springframework.version}</version>
                </dependency>
        
                <dependency>
                    <groupId>org.springframework</groupId>
                    <artifactId>spring-jdbc</artifactId>
                    <version>${org.springframework.version}</version>
                </dependency>
        
                <dependency>
                    <groupId>org.springframework</groupId>
                    <artifactId>spring-tx</artifactId>
                    <version>${org.springframework.version}</version>
                </dependency>
        
                <dependency>
                    <groupId>org.springframework</groupId>
                    <artifactId>spring-test</artifactId>
                    <version>${org.springframework.version}</version>
                </dependency>
        
        
                <dependency>
                    <groupId>org.aspectj</groupId>
                    <artifactId>aspectjweaver</artifactId>
                    <version>1.7.3</version>
                </dependency>
        
                <dependency>
                    <groupId>org.mybatis</groupId>
                    <artifactId>mybatis-spring</artifactId>
                    <version>${org.mybatis.spring.version}</version>
                </dependency>
                <dependency>
                    <groupId>org.mybatis</groupId>
                    <artifactId>mybatis</artifactId>
                    <version>${org.mybatis.version}</version>
                </dependency>
        
                <dependency>
                    <groupId>org.aspectj</groupId>
                    <artifactId>aspectjrt</artifactId>
                    <version>1.6.11</version>
                </dependency>
        
                <dependency>
                    <groupId>org.codehaus.jackson</groupId>
                    <artifactId>jackson-mapper-asl</artifactId>
                    <version>1.9.12</version>
                </dependency>
        
                <dependency>
                    <groupId>commons-dbcp</groupId>
                    <artifactId>commons-dbcp</artifactId>
                    <version>1.4</version>
                    <!--<scope>runtime</scope>-->
                </dependency>
        
        
                <dependency>
                    <groupId>ch.qos.logback</groupId>
                    <artifactId>logback-classic</artifactId>
                    <version>1.1.2</version>
                    <scope>compile</scope>
                </dependency>
                <dependency>
                    <groupId>ch.qos.logback</groupId>
                    <artifactId>logback-core</artifactId>
                    <version>1.1.2</version>
                    <scope>compile</scope>
                </dependency>
        
                <dependency>
                    <groupId>mysql</groupId>
                    <artifactId>mysql-connector-java</artifactId>
                    <version>5.1.6</version>
                </dependency>
        
                <dependency>
                    <groupId>com.google.guava</groupId>
                    <artifactId>guava</artifactId>
                    <version>20.0</version>
                </dependency>
        
        
                <dependency>
                    <groupId>org.apache.commons</groupId>
                    <artifactId>commons-lang3</artifactId>
                    <version>3.5</version>
                </dependency>
        
        
                <dependency>
                    <groupId>commons-collections</groupId>
                    <artifactId>commons-collections</artifactId>
                    <version>3.2.1</version>
                </dependency>
        
        
                <dependency>
                    <groupId>junit</groupId>
                    <artifactId>junit</artifactId>
                    <version>4.12</version>
                    <!--<scope>test</scope>-->
                </dependency>
        
                <dependency>
                    <groupId>joda-time</groupId>
                    <artifactId>joda-time</artifactId>
                    <version>2.3</version>
                </dependency>
        
        
                <!-- id加密解密 -->
                <dependency>
                    <groupId>org.hashids</groupId>
                    <artifactId>hashids</artifactId>
                    <version>1.0.1</version>
                </dependency>
        
        
                <!-- ftpclient -->
                <dependency>
                    <groupId>commons-net</groupId>
                    <artifactId>commons-net</artifactId>
                    <version>3.1</version>
                </dependency>
        
                <!-- file upload -->
        
                <!-- https://mvnrepository.com/artifact/commons-fileupload/commons-fileupload -->
                <dependency>
                    <groupId>commons-fileupload</groupId>
                    <artifactId>commons-fileupload</artifactId>
                    <version>1.2.2</version>
                </dependency>
        
                <dependency>
                    <groupId>commons-io</groupId>
                    <artifactId>commons-io</artifactId>
                    <version>2.0.1</version>
                </dependency>
        
        
                <!-- mybatis pager -->
        
                <dependency>
                    <groupId>com.github.pagehelper</groupId>
                    <artifactId>pagehelper</artifactId>
                    <version>4.1.0</version>
                </dependency>
        
                <dependency>
                    <groupId>com.github.miemiedev</groupId>
                    <artifactId>mybatis-paginator</artifactId>
                    <version>1.2.17</version>
                </dependency>
        
                <dependency>
                    <groupId>com.github.jsqlparser</groupId>
                    <artifactId>jsqlparser</artifactId>
                    <version>0.9.4</version>
                </dependency>
        
        
                <!-- alipay -->
                <dependency>
                    <groupId>commons-codec</groupId>
                    <artifactId>commons-codec</artifactId>
                    <version>1.10</version>
                </dependency>
                <dependency>
                    <groupId>commons-configuration</groupId>
                    <artifactId>commons-configuration</artifactId>
                    <version>1.10</version>
                </dependency>
                <dependency>
                    <groupId>commons-lang</groupId>
                    <artifactId>commons-lang</artifactId>
                    <version>2.6</version>
                </dependency>
                <dependency>
                    <groupId>commons-logging</groupId>
                    <artifactId>commons-logging</artifactId>
                    <version>1.1.1</version>
                </dependency>
                <dependency>
                    <groupId>com.google.zxing</groupId>
                    <artifactId>core</artifactId>
                    <version>2.1</version>
                </dependency>
                <dependency>
                    <groupId>com.google.code.gson</groupId>
                    <artifactId>gson</artifactId>
                    <version>2.3.1</version>
                </dependency>
                <dependency>
                    <groupId>org.hamcrest</groupId>
                    <artifactId>hamcrest-core</artifactId>
                    <version>1.3</version>
                </dependency>
        
                <dependency>
                    <groupId>redis.clients</groupId>
                    <artifactId>jedis</artifactId>
                    <version>2.9.0</version>
                </dependency>
                <dependency>
                    <groupId>junit</groupId>
                    <artifactId>junit</artifactId>
                    <version>4.12</version>
                    <scope>test</scope>
                </dependency>
            </dependencies>
            <build>
                <finalName>ShoppingTB</finalName>
                <plugins>
                    <plugin>
                        <groupId>org.mybatis.generator</groupId>
                        <artifactId>mybatis-generator-maven-plugin</artifactId>
                        <version>1.3.2</version>
                        <configuration>
                            <verbose>true</verbose>
                            <overwrite>true</overwrite>
                        </configuration>
                    </plugin>
        
                    <!-- codinglixh's ll maven的核心插件之-complier插件默认只支持编译Java 1.4，因此需要加上支持高版本jre的配置，在pom.xml里面加上 增加编译插件 -->
                    <plugin>
                        <groupId>org.apache.maven.plugins</groupId>
                        <artifactId>maven-compiler-plugin</artifactId>
                        <configuration>
                            <source>1.8</source>
                            <target>1.8</target>
                            <encoding>UTF-8</encoding>
                            <compilerArguments>
                                <extdirs>${project.basedir}/src/main/webapp/WEB-INF/lib</extdirs>
                            </compilerArguments>
                        </configuration>
                    </plugin>
                </plugins>
            </build>
        </project>


> pom.xml 详解后续补上。这是完整项目所需要的jar

- 项目package创建

![image text](https://raw.githubusercontent.com/codingLeexh/MarkDownPhotos/master/img/QQ%E5%9B%BE%E7%89%8720180224150023.png)

> 项目基本初始化完成，接下来准备coding~


### Coding前的准备工作

> 本项目使用了mybatis的一个插件自动生成代码(mybatis-generator生成pojo和mapper.xml关于此插件的详解，后续补上),所以先设计好数据库

#### **数据库表分析**：

- 用户表：tb_user
        
        CREATE TABLE `tb_user` (
          `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '用户表id',
          `username` varchar(50) NOT NULL COMMENT '用户名',
          `password` varchar(50) NOT NULL COMMENT '用户密码，MD5加密',
          `email` varchar(50) DEFAULT NULL,
          `phone` varchar(20) DEFAULT NULL,
          `question` varchar(100) DEFAULT NULL COMMENT '找回密码问题',
          `answer` varchar(100) DEFAULT NULL COMMENT '找回密码答案',
          `role` int(4) NOT NULL COMMENT '角色0-管理员,1-普通用户',
          `create_time` datetime NOT NULL COMMENT '创建时间',
          `update_time` datetime NOT NULL COMMENT '最后一次更新时间',
          PRIMARY KEY (`id`),
          UNIQUE KEY `user_name_unique` (`username`) USING BTREE
        ) ENGINE=InnoDB AUTO_INCREMENT=22 DEFAULT CHARSET=utf8;
        
        
- 购物车：tb_cart
        
        CREATE TABLE `tb_cart` (
          `id` int(11) NOT NULL AUTO_INCREMENT,
          `user_id` int(11) NOT NULL,
          `product_id` int(11) DEFAULT NULL COMMENT '商品id',
          `quantity` int(11) DEFAULT NULL COMMENT '数量',
          `checked` int(11) DEFAULT NULL COMMENT '是否选择,1=已勾选,0=未勾选',
          `create_time` datetime DEFAULT NULL COMMENT '创建时间',
          `update_time` datetime DEFAULT NULL COMMENT '更新时间',
          PRIMARY KEY (`id`),
          KEY `user_id_index` (`user_id`) USING BTREE
        ) ENGINE=InnoDB AUTO_INCREMENT=146 DEFAULT CHARSET=utf8;
        
        
- 商品分类：tb_category
        
        CREATE TABLE `tb_category` (
          `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '类别Id',
          `parent_id` int(11) DEFAULT NULL COMMENT '父类别id当id=0时说明是根节点,一级类别',
          `name` varchar(50) DEFAULT NULL COMMENT '类别名称',
          `status` tinyint(1) DEFAULT '1' COMMENT '类别状态1-正常,2-已废弃',
          `sort_order` int(4) DEFAULT NULL COMMENT '排序编号,同类展示顺序,数值相等则自然排序',
          `create_time` datetime DEFAULT NULL COMMENT '创建时间',
          `update_time` datetime DEFAULT NULL COMMENT '更新时间',
          PRIMARY KEY (`id`)
        ) ENGINE=InnoDB AUTO_INCREMENT=100032 DEFAULT CHARSET=utf8;
        
        
- 订单表：tb_order
        
        CREATE TABLE `tb_order` (
          `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '订单id',
          `order_no` bigint(20) DEFAULT NULL COMMENT '订单号',
          `user_id` int(11) DEFAULT NULL COMMENT '用户id',
          `shipping_id` int(11) DEFAULT NULL,
          `payment` decimal(20,2) DEFAULT NULL COMMENT '实际付款金额,单位是元,保留两位小数',
          `payment_type` int(4) DEFAULT NULL COMMENT '支付类型,1-在线支付',
          `postage` int(10) DEFAULT NULL COMMENT '运费,单位是元',
          `status` int(10) DEFAULT NULL COMMENT '订单状态:0-已取消-10-未付款，20-已付款，40-已发货，50-交易成功，60-交易关闭',
          `payment_time` datetime DEFAULT NULL COMMENT '支付时间',
          `send_time` datetime DEFAULT NULL COMMENT '发货时间',
          `end_time` datetime DEFAULT NULL COMMENT '交易完成时间',
          `close_time` datetime DEFAULT NULL COMMENT '交易关闭时间',
          `create_time` datetime DEFAULT NULL COMMENT '创建时间',
          `update_time` datetime DEFAULT NULL COMMENT '更新时间',
          PRIMARY KEY (`id`),
          UNIQUE KEY `order_no_index` (`order_no`) USING BTREE
        ) ENGINE=InnoDB AUTO_INCREMENT=118 DEFAULT CHARSET=utf8;
        
        
- 全部订单：tb_order_item
        
        CREATE TABLE `tb_order_item` (
          `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '订单子表id',
          `user_id` int(11) DEFAULT NULL,
          `order_no` bigint(20) DEFAULT NULL,
          `product_id` int(11) DEFAULT NULL COMMENT '商品id',
          `product_name` varchar(100) DEFAULT NULL COMMENT '商品名称',
          `product_image` varchar(500) DEFAULT NULL COMMENT '商品图片地址',
          `current_unit_price` decimal(20,2) DEFAULT NULL COMMENT '生成订单时的商品单价，单位是元,保留两位小数',
          `quantity` int(10) DEFAULT NULL COMMENT '商品数量',
          `total_price` decimal(20,2) DEFAULT NULL COMMENT '商品总价,单位是元,保留两位小数',
          `create_time` datetime DEFAULT NULL,
          `update_time` datetime DEFAULT NULL,
          PRIMARY KEY (`id`),
          KEY `order_no_index` (`order_no`) USING BTREE,
          KEY `order_no_user_id_index` (`user_id`,`order_no`) USING BTREE
        ) ENGINE=InnoDB AUTO_INCREMENT=135 DEFAULT CHARSET=utf8;
        
        
- 支付信息：tb_pay_info
        
        CREATE TABLE `tb_pay_info` (
          `id` int(11) NOT NULL AUTO_INCREMENT,
          `user_id` int(11) DEFAULT NULL COMMENT '用户id',
          `order_no` bigint(20) DEFAULT NULL COMMENT '订单号',
          `pay_platform` int(10) DEFAULT NULL COMMENT '支付平台:1-支付宝,2-微信',
          `platform_number` varchar(200) DEFAULT NULL COMMENT '支付宝支付流水号',
          `platform_status` varchar(20) DEFAULT NULL COMMENT '支付宝支付状态',
          `create_time` datetime DEFAULT NULL COMMENT '创建时间',
          `update_time` datetime DEFAULT NULL COMMENT '更新时间',
          PRIMARY KEY (`id`)
        ) ENGINE=InnoDB AUTO_INCREMENT=61 DEFAULT CHARSET=utf8;

        
- 商品详情：tb_product
        
        CREATE TABLE `tb_product` (
          `id` int(11) NOT NULL AUTO_INCREMENT COMMENT '商品id',
          `category_id` int(11) NOT NULL COMMENT '分类id,对应tb_category表的主键',
          `name` varchar(100) NOT NULL COMMENT '商品名称',
          `subtitle` varchar(200) DEFAULT NULL COMMENT '商品副标题',
          `main_image` varchar(500) DEFAULT NULL COMMENT '产品主图,url相对地址',
          `sub_images` text COMMENT '图片地址,json格式,扩展用',
          `detail` text COMMENT '商品详情',
          `price` decimal(20,2) NOT NULL COMMENT '价格,单位-元保留两位小数',
          `stock` int(11) NOT NULL COMMENT '库存数量',
          `status` int(6) DEFAULT '1' COMMENT '商品状态.1-在售 2-下架 3-删除',
          `create_time` datetime DEFAULT NULL COMMENT '创建时间',
          `update_time` datetime DEFAULT NULL COMMENT '更新时间',
          PRIMARY KEY (`id`)
        ) ENGINE=InnoDB AUTO_INCREMENT=30 DEFAULT CHARSET=utf8;
        
        
- 收货地址：tb_shipping
        
        CREATE TABLE `tb_shipping` (
          `id` int(11) NOT NULL AUTO_INCREMENT,
          `user_id` int(11) DEFAULT NULL COMMENT '用户id',
          `receiver_name` varchar(20) DEFAULT NULL COMMENT '收货姓名',
          `receiver_phone` varchar(20) DEFAULT NULL COMMENT '收货固定电话',
          `receiver_mobile` varchar(20) DEFAULT NULL COMMENT '收货移动电话',
          `receiver_province` varchar(20) DEFAULT NULL COMMENT '省份',
          `receiver_city` varchar(20) DEFAULT NULL COMMENT '城市',
          `receiver_district` varchar(20) DEFAULT NULL COMMENT '区/县',
          `receiver_address` varchar(200) DEFAULT NULL COMMENT '详细地址',
          `receiver_zip` varchar(6) DEFAULT NULL COMMENT '邮编',
          `create_time` datetime DEFAULT NULL,
          `update_time` datetime DEFAULT NULL,
          PRIMARY KEY (`id`)
        ) ENGINE=InnoDB AUTO_INCREMENT=33 DEFAULT CHARSET=utf8;
        
> 数据表结构详解后续补上 

- 创建数据库：shoppingtb

- 创建数据表

![image text](https://raw.githubusercontent.com/codingLeexh/MarkDownPhotos/master/img/QQ%E5%9B%BE%E7%89%8720180224160645.png)

#### 使用mybatis-generator

- pom.xml中装载mybatis-generator
        
        <plugin>
              <groupId>org.mybatis.generator</groupId>
              <artifactId>mybatis-generator-maven-plugin</artifactId>
              <version>1.3.2</version>
              <configuration>
              <verbose>true</verbose>
              <overwrite>true</overwrite>
              </configuration>
        </plugin>
        
- 创建配置mybatis-generator核心配置文件generatorConfig.xml
    
    resources文件夹下创建generatorConfig.xml
    
    具体配置：
    
            <?xml version="1.0" encoding="UTF-8"?>
            <!DOCTYPE generatorConfiguration
                    PUBLIC "-//mybatis.org//DTD MyBatis Generator Configuration 1.0//EN"
                    "http://mybatis.org/dtd/mybatis-generator-config_1_0.dtd">
            
            <generatorConfiguration>
                <!--导入属性配置-->
                <properties resource="datasource.properties"></properties>
            
                <!--指定特定数据库的jdbc驱动jar包的位置-->
                <classPathEntry location="${db.driverLocation}"/>
            
                <context id="default" targetRuntime="MyBatis3">
            
                    <!-- optional，旨在创建class时，对注释进行控制 -->
                    <commentGenerator>
                        <property name="suppressDate" value="true"/>
                        <property name="suppressAllComments" value="true"/>
                    </commentGenerator>
            
                    <!--jdbc的数据库连接 -->
                    <jdbcConnection
                            driverClass="${db.driverClassName}"
                            connectionURL="${db.url}"
                            userId="${db.username}"
                            password="${db.password}">
                    </jdbcConnection>
            
            
                    <!-- 非必需，类型处理器，在数据库类型和java类型之间的转换控制-->
                    <javaTypeResolver>
                        <property name="forceBigDecimals" value="false"/>
                    </javaTypeResolver>
            
            
                    <!-- Model模型生成器,用来生成含有主键key的类，记录类 以及查询Example类
                        targetPackage     指定生成的model生成所在的包名
                        targetProject     指定在该项目下所在的路径
                    -->
            
                    <javaModelGenerator targetPackage="cn.codinglixh.pojo" targetProject="./src/main/java">
                        <!-- 是否允许子包，即targetPackage.schemaName.tableName -->
                        <property name="enableSubPackages" value="false"/>
                        <!-- 是否对model添加 构造函数 -->
                        <property name="constructorBased" value="true"/>
                        <!-- 是否对类CHAR类型的列的数据进行trim操作 -->
                        <property name="trimStrings" value="true"/>
                        <!-- 建立的Model对象是否 不可改变  即生成的Model对象不会有 setter方法，只有构造方法 -->
                        <property name="immutable" value="false"/>
                    </javaModelGenerator>
            
                    <!--mapper映射文件生成所在的目录 为每一个数据库的表生成对应的SqlMap文件 -->
            
                    <sqlMapGenerator targetPackage="mappers" targetProject="./src/main/resources">
                        <property name="enableSubPackages" value="false"/>
                    </sqlMapGenerator>
            
                    <!-- 客户端代码，生成易于使用的针对Model对象和XML配置文件 的代码
                            type="ANNOTATEDMAPPER",生成Java Model 和基于注解的Mapper对象
                            type="MIXEDMAPPER",生成基于注解的Java Model 和相应的Mapper对象
                            type="XMLMAPPER",生成SQLMap XML文件和独立的Mapper接口
                    -->
            
                    <!-- targetPackage：mapper接口dao生成的位置 -->
            
                    <javaClientGenerator type="XMLMAPPER" targetPackage="cn.codinglixh.dao" targetProject="./src/main/java">
                        <!-- enableSubPackages:是否让schema作为包的后缀 -->
                        <property name="enableSubPackages" value="false"/>
                    </javaClientGenerator>
            
            
                    <table tableName="tb_shipping" domainObjectName="Shipping" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false"></table>
                    <table tableName="tb_cart" domainObjectName="Cart" enableCountByExample="false" enableUpdateByExample="false"
                           enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
                    <table tableName="tb_cart_item" domainObjectName="CartItem" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false"></table>
                    <table tableName="tb_category" domainObjectName="Category" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false"></table>
                    <table tableName="tb_order" domainObjectName="Order" enableCountByExample="false" enableUpdateByExample="false"
                           enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
                    <table tableName="tb_order_item" domainObjectName="OrderItem" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false"></table>
                    <table tableName="tb_pay_info" domainObjectName="PayInfo" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false"></table>
                    <table tableName="tb_product" domainObjectName="Product" enableCountByExample="false"
                           enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false"
                           selectByExampleQueryId="false">
                        <columnOverride column="detail" jdbcType="VARCHAR"/>
                        <columnOverride column="sub_images" jdbcType="VARCHAR"/>
                    </table>
                    <table tableName="tb_user" domainObjectName="User" enableCountByExample="false" enableUpdateByExample="false"
                           enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            
            
                    <!--  mybatis插件的搭建 -->
                </context>
            </generatorConfiguration>

> 详解注意注释

- 创建导入的属性配置文件datasource.properties

        db.driverLocation=C://Users/self-consciousness/mysql-connector-java-5.1.6.jar
        db.driverClassName=com.mysql.jdbc.Driver
        db.url=jdbc:mysql://localhost:3306/shoppingtb?characterEncoding=utf-8
        db.username=root
        db.password=1234

> db.driverLocation指的是本地的mysql驱动包路径(你所下载下来的jar所在的文件夹，也可以在maven本地仓库)

- 用写好的配置文件生成java文件及*mapper.xml
    
    在IDEA右侧(默认)Maven Projects里，展开ShoppingTB Maven Webapp ,展开 Plugins ,展开mybatis-generator，双击mybatis-generator：generate(或者点击上面的运行键)
    
     预览：
     
     ![image text](https://raw.githubusercontent.com/codingLeexh/MarkDownPhotos/master/img/QQ%E5%9B%BE%E7%89%8720180224164109.png)
     
     > 运行
     
     ![image text](https://raw.githubusercontent.com/codingLeexh/MarkDownPhotos/master/img/QQ%E5%9B%BE%E7%89%8720180224164214.png)
     
     > 成功
     
     ![image text](https://raw.githubusercontent.com/codingLeexh/MarkDownPhotos/master/img/QQ%E5%9B%BE%E7%89%8720180224164301.png)
     
     > 生成的文件(resources文件夹下有一个mappers文件夹，存放生成的mybatis所需要的xml文件，图略)

### 用户模块

