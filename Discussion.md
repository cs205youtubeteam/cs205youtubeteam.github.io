Challenges: Our primary challenge was getting the various software dependencies to work well with each other:
The installation of Elephas uses a version of PySpark which is incompatible with Scala on the EMR, and we had to manually install a compatible version.
To be able to launch AMIs on EMR, the AMI must be created from a compatible Amazon Linux EC2 instance. It took much trial and error to properly provision the AMI and EMR.
The amount of data is very large and mounting it on HDFS took very long, so we instead used a 30GB subset as an example, and left it to future work to expand to the full 1.5TB. Additionally, TFRecords is not natively supported on Spark and we had to install Apache Maven and a Tensorflow-Spark connector.

Overheads: The main overhead was the communication of parameters from worker nodes to master node. Secondary to this was the launching of the Spark application across the cluster, which plays a small role in runtime.
