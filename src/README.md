搭建SSM运行的基础模板，本模板没有实现任何功能
1.创建maven工程
	新建maven project，生成后会缺少web.xml，报错
		1）右键-》java EE Tools-》General... 自动生成
		2）右键-》properties-》project facets，将Dynamic Web Module 勾去在勾上，下方会有提示，配   		置WEB-INF，点进去，修改存放路径
	会出各种问题，先进行一些设置
		1）window-》properties-》use settings，设置maven的settings.xml,有默认值，可以修改成下载    
		 的maven的setting.xml，保存的目录\apache-maven-3.5.2\conf\settings.xml
		 	可以配置settings.xml
		 	1》添加镜像，这样下载jar包快了好多
		 	<mirrors>
		 		<mirror>
		 			<id>alimaven</id>
		 			<name>aliyun maven</name>
		 			<url>http://maven.aliyun.com/newus/content/groups/public/</url>
		 			<mirrorOf>central</mirrorOf>
		 		</mirror>
		 	</mirrors>
		 	2》添加配置，会少很多问题
		 	<profiles>
		 		<profile>
		 			<id>jdk17</id>
		 			<activation>
		 				<activeByDefault>true</activeByDefault>
		 				<jdk>1.7</jdk>
		 			</activation>
		 			<properties>
		 				<maven.compiler.source>1.7</maven.compiler.source>
		 				<maven.compiler.target>1.7</maven.compiler.target>
	 				   <maven.compiler.compilerVersion>1.7</maven.compiler.compilerVersion>
		 			</properties>
		 		</profile>
		 	</profiles>
2.引入jar包
	spring:spring jdbc;spring aspect
	springmvc:spring webmvc
	mybatis:mybatis;mybatis spring
	数据库连接池，驱动包:C3p0:JDBC DataSources/Resource Pools;MySQL Connector/J
	其他，项目需要时引入：jstl，servlet-api，junit
	步骤：
	1.到maven的中央仓库  http://mvnrepository.com/
	2.搜索相应的项目
	3.得到导入的
		<dependency>........</dependency>
		
		
BootStrap：提供了很多好看的样式，是一个很大的样式库	


4.编写ssm整合的关键配置文件
	web.xml:直接到配置文件中看就可以了，有注解，挺详细的
	spring:配置文件的核心点包括：数据源，mybatis的整合，事务控制
	springmvc
	mybatis:
		使用mybatis的逆向工程生成对应的bean以及mapper
			1.导入jar包，mybatis generator
			2.在项目路径下建立mbg.xml，修改配置
			3.使用代码逆向生成bean
				代码获取到http://www.mybatis.org/generator/running/runningWithJava.html
	
	
	
	
问题：eclipse 上xml 文件打开后底下不会出现namespace等信息的原因
https://www.cnblogs.com/liuyungao/p/6213997.html


github上传：
	