## Apache Hadoop and YARN

The Apache Hadoop software library is a framework that allows for the distributed processing of large data sets across computer clusters using simple programming models. 
Apache Hadoop works using master-slave architecture.


## Download Apache Hadoop

Information about the versions of each software can be seen below:
- Apache Hadoop 2.7.2: https://archive.apache.org/dist/hadoop/core/hadoop-2.7.2/

## YARN Configuration

To create the HDFS distributed storage environment, a directory must be created for namenode and datanode. Remember that the directory must be created manually and edited in the file ```hdfs-site.xml``` in ```hadoop-2.7.2/etc/hadoop```. For the Master-node, we must inform the datanode and namenode directory. 
In the case of slave-nodes, the namenode directory must not exist.


