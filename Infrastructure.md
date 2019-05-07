We turned to a parallel architecture to address challenges relating to both Big Data and Big Compute. 

We used Spark to partition and distribute the 1.5 TB YouTube 8M dataset on a Hadoop Distributed Filesystem (HDFS), as well as to handle the communication between nodes. We used the deep learning library Tensorflow to train our model. We deployed multiple Amazon Web Services (AWS) Elastic Map Reduce (EMR) m4.xlarge instances to construct our cluster.

We initially mounted an S3 bucket as a drive on the local filesystem, and then distributed our data with HDFS. However, we found that it was easier and faster to simply point Spark directly to the S3 bucket. We used the Tensorflow-Spark Connector library which can load tfrecords into Spark DataFrames. We built an Amazon Machine Image (AMI) that included installations of TensorFlow in conjunction with Elephas, a library for distributed ML training. We spun up the EMR cluster using this AMI to allow elastic scalability without manual installation of dependencies. We ran all experiments with a single master and n=1,2,4,8,15 workers.

Software versions:
Amazon Linux 2018.03.0, Python 3.6, EMR 5.32, Hadoop YARN 2.8, Spark 2.4, Scala 2.11, Java 8, Tensorflow 1.13







