## Apache Hadoop and YARN

The Apache Hadoop software library is a framework that allows for the distributed processing of large data sets across computer clusters using simple programming models. 
Apache Hadoop works using master-slave architecture.


## Download Apache Hadoop

Information about the versions of each software can be seen below:
- Apache Hadoop 2.7.2: https://archive.apache.org/dist/hadoop/core/hadoop-2.7.2/

## YARN Configuration

### hdfs-site.xml

To create the HDFS distributed storage environment, a directory must be created for namenode and datanode. Remember that the directory must be created manually and edited in the file ```hdfs-site.xml``` in ```hadoop-2.7.2/etc/hadoop```. For the Master-node, we must inform the datanode and namenode directory. 
In the case of slave-nodes, the namenode directory must not exist.

```
<property>
 <name>dfs.replication</name>
 <value>1</value>
</property>
<property>
 <name>dfs.namenode.name.dir</name>
 <value>/state/hdfs/namenode</value>
 <final>true</final>
</property>
<property>
 <name>dfs.datanode.data.dir</name>
 <value>/state/hdfs/datanode</value>
 <final>true</final>
</property>
<property>
 <name>dfs.datanode.synconclose</name>
 <value>true</value>
</property>
```

### core-site.xml 

The next step is to edit the ```core-site.xm```l file. In this case, in the ```fs.defaultFS``` field, you must inform the hdfs address and the port of the machine that plays the role of Masternode. After setting up the ```core-site.xml```, we can replicate all the machines in the cluster, since these machines must connect at the hdfs address of the master-node.

```
<property>
 <name>fs.defaultFS</name>
 <value>hdfs://master-node:9000</value>
</property>
```
