## 配置环境
1. scala:2.13
2. zookeeper:3.8.3
3. gradle:8.5-all(配置好本地gradle) 会自动下载8.5的包装,
   如果因为网络问题下载不下来，可以通过其他方式下载下来后通过`distributionUrl=file:///D:/gradle/gradle-8.5-all.zip` 制定具体地址
4. 修改相关配置文件。 build.gradle 修改为国内镜像。
5. 注释掉 build.gradle 中965-970 行代码（日志框架依赖，否则启动不起来）
6. 启动zk(本地zk即可)
7. 启动core 模块中的kafka.kafka 

   (program variable `-Dlog4j.configuration=file:D:\idea-project\kafka\config/log4j.properties` )
   (vm option `D:\idea-project\kafka\config\server.properties`)

## 创建topic 流程
   客户端： `kafka.tools.TopicCommand#createTopic`  --> `adminClient.createTopics`  --> 
   