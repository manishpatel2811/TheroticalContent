# Installations and Configurations

## MAC  
-> Follow this to install java  
https://www.tutorialspoint.com/apache_kafka/apache_kafka_installation_steps.htm

## Centos

### install java 

-> install
sudo yum install java-1.8.0-openjdk-devel
https://linuxize.com/post/install-java-on-centos-7/

-> path set
paste this under ~/.bash_profile

export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
export JAVA_PATH=$JAVA_HOME
export PATH=$PATH:$JAVA_HOME/bin


save it and then do source ~/.bash_profile

https://parichay.inflibnet.ac.in/documents/JAVA_HOME.pdf

-

### ZooKeeper Installation

-> Install zookeeper


cd /opt
sudo yum install -y wget
sudo wget https://archive.apache.org/dist/zookeeper/zookeeper-3.4.9/zookeeper-3.4.9.tar.gz
sudo tar -zxf zookeeper-3.4.9.tar.gz
cd zookeeper-3.4.9
sudo mkdir data

-> create Config file  

vi conf/zoo.conf
tickTime=2000
dataDir=/path/to/zookeeper/data
clientPort=2181
initLimit=5
syncLimit=2

-> start
bin/zkServer.sh start

check 
bin/zkCli.sh

stop 
bin/zkServer.sh stop

# Kafka Installation

cd /opt
wget http://archive.apache.org/dist/kafka/0.9.0.0/kafka_2.11-0.9.0.0.tgz
sudo tar -xvf kafka_2.11-0.9.0.0.tgz
cd kafka_2.11.0.9.0.0

start server

bin/kafka-server-start.sh config/server.properties

stop server

bin/kafka-server-stop.sh config/server.properties


https://www.tutorialspoint.com/apache_kafka/apache_kafka_installation_steps.htm
=============
