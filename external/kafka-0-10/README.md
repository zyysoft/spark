### Build
```
mvn clean scala:compile compile package -DskipTests
cp target/spark-streaming-kafka-0-10_2.11-2.2.0.jar /opt/m2_repo/org/apache/spark/spark-streaming-kafka-0-10_2.11/2.2.0/
cp target/spark-streaming-kafka-0-10_2.11-2.2.0-sources.jar /opt/m2_repo/org/apache/spark/spark-streaming-kafka-0-10_2.11/2.2.0/

scp target/spark-streaming-kafka-0-10_2.11-2.2.0.jar root@BI-HD12:/opt/zhaoyaoyuan

mvn deploy:deploy-file -DgroupId=org.apache.spark -DartifactId=spark-streaming-kafka-0-10_2.11 -Dversion=2.2.0 -Dfile=target/spark-streaming-kafka-0-10_2.11-2.2.0.jar -Durl=http://dev-bi-cdh07:8081/repository/bi-nexus/ -DrepositoryId=bi-nexus
```
### 优化
* 支持每个KafkaRDD处理的最大消息量