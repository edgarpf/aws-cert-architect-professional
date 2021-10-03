# Tips for AWS Certified Solutions Architect – Professional
* Kinesis Agent cannot write to a Kinesis Firehose for which the delivery stream source is already set as Kinesis Data Streams.
* The throughput of an Amazon Kinesis data stream is designed to scale without limits via increasing the number of shards within a data stream, a manual process.
* Configure an S3 VPC endpoint and create an S3 bucket policy to allow access only from this VPC endpoint.
* SCPs do not affect service-linked role.
* SCPs affect all users and roles in attached accounts, including the root user.
* If a user or role has an IAM permission policy that grants access to an action that is either not allowed or explicitly denied by the applicable SCPs, the user or role can't perform that action.
* Use AWS DataSync to automate and accelerate online data transfers to AWS storage services like S3, EFS and Fsx.
* Amazon SNS message can deliver many messages to AWS Lambda and cross the account concurrency quota for Lambda, so you will need to contact AWS support to raise the account limit.
* Create separate cache behaviors for static and dynamic content using CloudFront to avoid a high cache miss rate.
* AWS recommends not to configure caching based on values in the Date and User-Agent headers, because these headers have numerous possible values and caching based on their values could cause CloudFront to forward significantly more requests to your origin.
* API Gateway creates RESTful APIs that enable stateless client-server communication and API Gateway also creates WebSocket APIs that adhere to the WebSocket protocol, which enables stateful, full-duplex communication between client and server.
* Use VPC sharing to share one or more subnets with other AWS accounts belonging to the same parent organization from AWS Organizations.
* By default, an S3 object is owned by the AWS account that uploaded it. So the S3 bucket owner will not implicitly have access to the objects written by Redshift cluster.
* Use Centralized VPC Endpoints for connecting with multiple VPCs, also known as shared services VPC.
* AWS Global Accelerator can be used to blue/green deployment without being subject to DNS caching on client devices and internet resolvers.
* Use Amazon Aurora Global Database to enable fast local reads with low latency in each region.
* Use S3 Glacier vault to store the sensitive archived data and then use a vault lock policy to enforce compliance controls.
* The primary and standby DB instances are upgraded at the same time for RDS MySQL Multi-AZ. All instances are upgraded at the same time for Aurora MySQL.
* Read Replicas can be manually promoted to a standalone database instance for RDS MySQL whereas Read Replicas for Aurora MySQL can be promoted to the primary instance.
* Multi-AZ deployments for both RDS MySQL and Aurora MySQL follow synchronous replication.
* Use message timers to postpone the delivery of certain messages to the SQS queue.
* CloudWatch Events cannot trigger a Lambda function upon a new file upload in S3 as this event pattern is not supported.
* When cross-zone load balancing is enabled, each load balancer node distributes the same traffic percentage across the registered targets in all enabled Availability Zones.
![imagem](https://i.ibb.co/MNgXyGM/imagem.jpg)
* Use AWS Kinesis Data Streams to facilitate multiple applications consume same streaming data concurrently and independently