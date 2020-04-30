mybaits的入门案例

**环境搭建**

第一步：创建maven工程，导入坐标

第二步：创建实体类和dao接口

第三步：创建mybatis的主配置文件 SqlMapConfig.xml

第四步：创建映射配置文件UserDao.xml


**环境搭建的注意事项**

第一个：创建Userdao.xml和Userdao.java是名称是为了和我们之前的知识保持一致。在mybatis中它把持久层的操作接口名称和映射文件叫做mapper
所以UserDao 和UserMapper是一样的

第二个：在idea创建目录/包是不一样	

第三个：mybatis的映射配置文件位置必须和dao接口的包结构相同

第四个：映射配置文件的mapper标签，namespace的取值必须是dao接口的全限定类名

第五个：映射配置文件的操作配置，必须是dao接口的方法名

如果我们遵从了以上点之后，我们在开发中无须再写dao的实现类。

**mybatis入门案例**

第一步：读取配置文件

第二步：创建SqlSessionFactory工厂

第三步：创建SqlSession

第四步：创建Dao接口的代理对象

第五步：执行dao中的方法

第六步：释放资源

注意事项：不要忘记，在映射配置中告知mybatis要封装到哪个配置类
配置的方式，是全限定类名。

**mybatis涉及到的设计模式**

创建工厂，mybatis使用了构建者模式，builder是构建者，把对象创建的细节隐藏。

生产sqlsession，使用了工厂模式，降低类之间的依赖关系，使我们不用重新编译部署。]

代理模式，创建一个Dao一个接口的实现类。不修改源码的基础上，对已有方法进行增强。
