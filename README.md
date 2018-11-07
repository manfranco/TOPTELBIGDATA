# TOPTELBIGDATA
Proyecto Tópicos de telemática Big data

## Prerequisites:
* Scala 2.11^
* Java 7^

## Installation:

* Clone project repository
```
git clone https://github.com/manfranco/TOPTELBIGDATA

cd TOPTELBIGDATA
```
* Download and untar Apache ZooKeper 3.4.13
```
wget https://www-us.apache.org/dist/zookeeper/zookeeper-3.4.13/zookeeper-3.4.13.tar.gz
tar xvf zookeeper-3.4.13.tar.gz
```
* Download and untar Spark 1.6.3
```
wget https://archive.apache.org/dist/spark/spark-1.6.3/spark-1.6.3-bin-hadoop2.6.tgz
tar xvf spark-1.6.3-bin-hadoop2.6.tgz
```
* Compile Kafka Producer
```
javac -cp ".:./lib/*" KafkaTwitterProducer.java
```
* Compile Spark program
sbt package

## How to run:


* Start the ZooKeper server

```
./zookeeper-3.4.13/bin/zkServer.sh Start
```

* Run Kafka Producer

```
java -cp ".:./lib/*" KafkaTwitterProducer FM3XYCkK6VROg9tT0AwgO2aT9 n7pCzLTU409Tu0GEzbEMY7uNCsTrDzkSZdxaEd1TuGtVjOipa8 106575202-atb95fQu93yu8zLKuBYpeOtm1DwUR60oXJ3BKqdI uxUWr1b3f5B5dzkORM41zoQFOg6aZEoTz7lq15DUDasvb [channel] [topic]
```

* Run Spark program

```
./spark-1.6.3-bin-hadoop2.6/bin/spark-submit --packages org.apache.spark:spark-streaming-kafka_2.10:1.6.0 --class "KafkaWordCount" --master local[4] target/scala-2.10/spark-kafka-project_2.10-1.0.jar localhost:2181 [groupname] [channel] [thread count]
```
