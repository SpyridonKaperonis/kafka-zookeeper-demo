# Kafka-zookeeper-demo

## Description

In this demo I will install Kafka and run it with zookeeper. 

## Installation

- Download Kafka from [https://www.apache.org/dyn/closer.cgi?path=/kafka/2.7.0/kafka_2.13-2.7.0.tgz](https://www.apache.org/dyn/closer.cgi?path=/kafka/2.7.0/kafka_2.13-2.7.0.tgz)

1. Extract the .tgz in C:\ 

1. Environment variables
- JAVA_HOME = C:\Program Files\OpenJDK\jdk-version folder
- KAFKA_HOME = C:\kafka-version folder
- M2_HOME = C:\ProgramData\chocolatey\lib\maven\apache-maven-version

- In path: %JAVA_HOME%\bin
- In path: %M2_HOME%\bin
- In path: %KAFKA_HOME%\bin
- In path: %KAFKA_HOME%\bin\windows

## Commands 

1. First PowerShell:  ``` .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties ```

1. Second PowerShell window: ``` .\bin\windows\kafka-server-start.bat .\config\server.properties ```

1. Third PowerShell window: ``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic quick-chat ``` and ``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list ```

1. Fourth PowerShell window: ``` .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic quick-chat ```

1. Fifth PowerShell window: ``` .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic quick-chat --from-beginning ```


## Debugging

- You may need to uncomment the ``` listeners=PLAINTEXT://localhost:9092 ```  line in /config/server.properties .  

 