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

首次提交**$ git push -u -f origin master**

创建分支**$ git checkout -b v1.0 origin/master**

查看分支**$ git branch**

提交分支**$ git push origin HEAD -u**

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


