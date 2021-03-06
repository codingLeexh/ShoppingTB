# 一个企业级电商项目

> 作者：codingLixh

- 时间：2018年2月24号

## 项目介绍：
    
- **工具及环境**：

        jdk_1.8,    IDEA2017,   Maven,  Git,    Github,    windows, Tomcat8.5
        
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
    

## 项目完整代码在分支v1.0上

# 温馨提示： 本项目持续更新，完整教程请耐心等待，本人尽快实现零基础教学
