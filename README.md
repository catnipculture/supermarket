# supermarket
Java：191 基于SSM的超市管理系统
> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

​

超市管理系统有管理员，用户，员工。

管理员功能有个人中心，用户管理，员工管理，供应商管理，商品分类管理，商品信息管理，商品入库管理，商品出库管理，商品采购管理，系统管理，订单管理等。

员工可以管理供应商，商品信息，入库和采购。

用户可以在前台购买商品

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：vue

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)


# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/c38708ca4af517d9f69b495bb5e1178e.png)

![image20241222002001034](https://i-blog.csdnimg.cn/img_convert/c7611eee6b15b1ccfd2e40d553204a2a.png)

### 项目截图

前台

![图片4](https://i-blog.csdnimg.cn/img_convert/a436bfa6cffe6f4edd0b8d761e6e98e8.png)

![图片5](https://i-blog.csdnimg.cn/img_convert/1d5d56a94eea10d8b6f9717d571826ad.png)

后台

![图片1](https://i-blog.csdnimg.cn/img_convert/2683e5bb6bdec5232f5a46eeed31d298.png)

![图片2](https://i-blog.csdnimg.cn/img_convert/05d78ee8e05f23dfee70d4456dac92ce.png)

![图片3](https://i-blog.csdnimg.cn/img_convert/9a449f84c6d095a17af36da30b7a8839.png)
### 代码

```
private PageLink createPageLink(int pageSize, int page, String textSearch, String sortProperty, String sortOrder) throws BizException {
        if (StringUtils.isNotEmpty(sortProperty)) {
            if (!ValidatorUtils.isValidProperty(sortProperty)) {
                throw new IllegalArgumentException("Invalid sort property");
            }
            SortOrder.Direction direction = SortOrder.Direction.ASC;
            if (StringUtils.isNotEmpty(sortOrder)) {
                try {
                    direction = SortOrder.Direction.valueOf(sortOrder.toUpperCase());
                } catch (IllegalArgumentException e) {
                    throw new BizException("Unsupported sort order '" + sortOrder + "'! Only 'ASC' or 'DESC' types are allowed.");
                }
            }
            SortOrder sort = new SortOrder(sortProperty, direction);
            return new PageLink(pageSize, page, textSearch, sort);
        } else {
            return new PageLink(pageSize, page, textSearch);
        }
    }
```
