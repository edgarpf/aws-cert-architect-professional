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
* Use AWS Kinesis Data Streams to facilitate multiple applications consume same streaming data concurrently and independently.
* If you have multiple AWS Site-to-Site VPN connections, you can provide secure communication between sites using the AWS VPN CloudHub. This enables your remote sites to communicate with each other, and not just with the VPC. Sites that use AWS Direct Connect connections to the virtual private gateway can also be part of the AWS VPN CloudHub.
* By default, FIFO queues support up to 300 transactions (API calls) per second (300 send, receive, or delete operations per second). When you batch 10 transactions per operation (maximum), FIFO queues can support up to 3,000 transactions per second.
* To use a certificate with an Application Load Balancer for the same site (the same fully qualified domain name, or FQDN, or set of FQDNs) in a different Region, you must request a new certificate for each Region in which you plan to use it.
* The following content types skip the regional edge cache:
  * Proxy methods PUT/POST/PATCH/OPTIONS/DELETE go directly to the origin.
  * Dynamic content, as determined at request time (cache-behavior configured to forward all headers).
* You can use AWS DMS data validation to ensure that your data has migrated accurately from the source to the target. DMS compares the source and target records and then reports any mismatches. 
* Process and analyze the AWS X-Ray traces and analyze HTTP methods to determine the root cause of the HTTP errors.
* AWS Direct Connect links your on-premises data center to an AWS Direct Connect location over a standard Ethernet fiber-optic cable. One end of the cable is connected to your router, the other to an AWS Direct Connect router. With this connection, you can create virtual interfaces directly to public AWS services (for example, to Amazon S3) or to Amazon VPC, bypassing internet service providers in your network path. An AWS Direct Connect location provides access to AWS in the Region with which it is associated.
* There are two types of Direct Connect connections:
  * Dedicated Connection: A physical Ethernet connection associated with a single customer. Customers can request a dedicated connection through the AWS Direct Connect console, the CLI, or the API. This supports speed of 1Gbps and 10Gbps.
  * Hosted Connection: A physical Ethernet connection that an AWS Direct Connect Partner provisions on behalf of a customer. Customers request a hosted connection by contacting a partner in the AWS Direct Connect Partner Program, who provisions the connection. This supports speed of 50Mbps, 100Mbps, 200Mbps, 300Mbps, 400Mbps, 500Mbps, 1Gbps, 2Gbps, 5Gbps, and 10Gbps.
* The following are the default rules for a default security group:
  * Allow inbound traffic from network interfaces (and their associated instances) that are assigned to the same security group.
  * Allows all outbound traffic.
  * So instance X can be pinged from other instances in the default security group.
* The following are the default rules for a security group that you create:
  * Allows no inbound traffic.
  * Allows all outbound traffic.
* Multi-AZ follows synchronous replication and spans at least two Availability Zones within a single region. Read Replicas follow asynchronous replication and can be within an Availability Zone, Cross-AZ, or Cross-Region.
* gp2 volumes deliver single-digit millisecond latencies and the ability to burst to 3,000 IOPS for extended periods of time. Between a minimum of 100 IOPS (at 33.33 GiB and below) and a maximum of 16,000 IOPS (at 5,334 GiB and above), baseline performance scales linearly at 3 IOPS per GiB of volume size.
* Cost of test file storage on S3 Standard < Cost of test file storage on EFS < Cost of test file storage on EBS.
* Require that your users access your private content by using special CloudFront signed URLs or signed cookies.
You should use a signed URL if you want to restrict access to individual files, for example, an installation download for your application. A signed URL includes additional information, for example, expiration date and time, that gives you more control over access to your content. On the other hand, CloudFront signed cookies allow you to control who can access your content when you don't want to change your current URLs or when you want to provide access to multiple restricted files, for example, all of the files in the members' area of a website.
* Each Snowball Edge device can handle 80TB of data.
* To use private hosted zones, DNS hostnames and DNS resolution should be enabled for the VPC.
* Use Enhanced Fanout feature of Kinesis Data Streams to support a great read throughput for the downstream applications.
* Use AWS Volume Gateway - Cached Volume - to store the most frequently accessed results locally for low-latency access while storing the full volume with all results in its Amazon S3 service bucket.
* Snowball Edge Storage Optimized is the optimal choice if you need to securely and quickly transfer dozens of terabytes to petabytes of data to AWS. 
* There are no S3 data transfer charges when data is transferred in from the internet.
* If you intend to reuse code in more than one Lambda function, you should consider creating a Lambda Layer for the reusable code.
* Since Lambda functions can scale extremely quickly, it's a good idea to deploy a CloudWatch Alarm that notifies your team when function metrics such as ConcurrentExecutions or Invocations exceeds the expected threshold.
* By default, Lambda functions always operate from an AWS-owned VPC and hence have access to any public internet address or public AWS APIs. Once a Lambda function is VPC-enabled, it will need a route through a NAT gateway in a public subnet to access public resources.
* Using Amazon Redshift Spectrum, you can efficiently query and retrieve structured and semistructured data from files in Amazon S3 without having to load the data into Amazon Redshift tables.
* You can configure various Docker networking modes that will be used by containers in your ECS task. The valid values are none, bridge, awsvpc, and host. The default Docker network mode is bridge.
  * If the network mode is set to none, the task's containers do not have external connectivity and port mappings can't be specified in the container definition.
  * If the network mode is bridge, the task utilizes Docker's built-in virtual network which runs inside each container instance.
  * If the network mode is host, the task bypasses Docker's built-in virtual network and maps container ports directly to the EC2 instance's network interface directly. In this mode, you can't run multiple instantiations of the same task on a single container instance when port mappings are used.
  * If the network mode is awsvpc, the task is allocated an elastic network interface, and you must specify a NetworkConfiguration when you create a service or run a task with the task definition. When you use this network mode in your task definitions, every task that is launched from that task definition gets its own elastic network interface (ENI) and a primary private IP address. The task networking feature simplifies container networking and gives you more control over how containerized applications communicate with each other and other services within your VPCs.
  * AWS strongly recommends that you don't attach SCPs to the root of your organization without thoroughly testing the impact that the policy has on accounts. Instead, create an OU that you can move your accounts into one at a time, or at least in small numbers, to ensure that you don't inadvertently lock users out of key services.