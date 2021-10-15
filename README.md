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
* It costs a lot of money to establish a Direct Connect connection which you rarely use. For a more cost-effective solution, you can configure a backup VPN connection for failover with your AWS Direct Connect connection. If you want a short-term or lower-cost solution, you might consider configuring a hardware VPN as a failover option for a Direct Connect connection. VPN connections are not designed to provide the same level of bandwidth available to most Direct Connect connections. Ensure that your use case or application can tolerate a lower bandwidth if you are configuring a VPN as a backup to a Direct Connect connection.
* AWS Server Migration Service is designed to simplify the end-to-end server migration process. AWS SMS currently supports the migration of on-premises virtual machines (VMs) as an agentless service using a virtual appliance. AWS SMS is an ideal solution to use when you are planning a scaled migration from VMware environments to AWS where the downtime, agentless tools, incremental replication, and testing the application before the cutover are critical considerations.
* When a Fargate task is launched, its elastic network interface requires a route to the Internet to pull container images. If you receive an error similar to the following when launching a task, it is because a route to the Internet does not exist:
***CannotPullContainerError: API error (500): Get https:<!--This is a comment-->//111122223333.dkr.ecr.us-east-1.amazonaws.com/v2/: net/http: request canceled while waiting for connection***
To resolve this issue, you can:
  * For tasks in public subnets, specify ENABLED for Auto-assign public IP when launching the task.
  * For tasks in private subnets, specify DISABLED for Auto-assign public IP when launching the task, and configure a NAT gateway in your VPC to route requests to the Internet.
* To connect to services such as EC2 using just Direct Connect you need to create a private virtual interface. However, if you want to encrypt the traffic flowing through Direct Connect, you will need to use the public virtual interface of DX to create a VPN connection that will allow access to AWS services such as S3, EC2, and other services. To connect to AWS resources that are reachable by a public/private IP address use a public/private virtual interface. If you want to establish a virtual private network (VPN) connection from your company network to an Amazon Virtual Private Cloud (Amazon VPC) over an AWS Direct Connect (DX) connection, you must use a public virtual interface for your DX connection.
* AWS Resource Access Manager (AWS RAM) enables you to share specified AWS resources that you own with other AWS accounts. To enable trusted access with AWS Organizations: From the AWS RAM CLI, use the enable-sharing-with-aws-organizations command.
* SCPs do not affect any service-linked role. Service-linked roles enable other AWS services to integrate with AWS Organizations and can't be restricted by SCPs.
* AWS CloudHSM is a cloud-based hardware security module (HSM) that enables you to easily generate and use your own encryption keys on the AWS Cloud. With CloudHSM, you can manage your own encryption keys and automate time-consuming administrative tasks for you, such as hardware provisioning, software patching, high-availability, and backups. This is the most secure way of ensuring that the key will not be moved outside of the AWS environment.
* For billing purposes, the consolidated billing feature of AWS Organizations treats all the accounts in the organization as one account. This means that all accounts in the organization can receive the hourly cost-benefit of Reserved Instances that are purchased by any other account. In the payer account, you can turn off Reserved Instance discount sharing on the Preferences page on the Billing and Cost Management console.
* You can use an AWS Direct Connect gateway to connect your AWS Direct Connect connection over a private virtual interface to one or more VPCs in your account that are located in the same or different Regions.
* In general, bucket owners pay for all Amazon S3 storage and data transfer costs associated with their bucket. A bucket owner, however, can configure a bucket to be a Requester Pays bucket. With Requester Pays buckets, the requester instead of the bucket owner pays the cost of the request and the data download from the bucket. The bucket owner always pays the cost of storing data.
* Amazon Connect provides a seamless omnichannel experience through a single unified contact center for voice and chat. Contact center agents and managers don’t have to learn multiple tools, because Amazon Connect has the same contact routing, queuing, analytics, and management tools in a single UI across voice, web chat, and mobile chat.
*  Amazon EC2 provides a Spot Instance interruption notice, which gives the instance a two-minute warning before it is interrupted. If Amazon ECS Spot Instance draining is enabled on the instance, ECS receives the Spot Instance interruption notice and places the instance in DRAINING status. When a container instance is set to DRAINING, Amazon ECS prevents new tasks from being scheduled for placement on the container instance. Service tasks on the draining container instance that are in the PENDING state are stopped immediately. If there are container instances in the cluster that are available, replacement service tasks are started on them.
* When a user requests your content, CloudFront typically serves the requested content regardless of where the user is located. If you need to prevent users in specific countries from accessing your content, you can use the CloudFront geo restriction feature.
* When you create a VPC using Amazon VPC, Route 53 Resolver automatically answers DNS queries for local VPC domain names for EC2 instances (ec2-192-0-2-44.compute-1.amazonaws.com) and records in private hosted zones (acme.example.com). For all other domain names, Resolver performs recursive lookups against public name servers. You also can integrate DNS resolution between Resolver and DNS resolvers on your network by configuring forwarding rules. Your network can include any network that is reachable from your VPC, such as the following:
  * The VPC itself.
  * Another peered VPC.
  * An on-premises network that is connected to AWS with AWS Direct Connect, a VPN, or a network address translation (NAT) gateway.
* There are 3 types of DeletionPolicy Options:
  * Delete
  * Retain
  * Snapshot

For Delete, CloudFormation deletes the resource and all its contents if applicable during stack deletion. For Retain, CloudFormation keeps the resource without deleting the resource or its contents when its stack is deleted. For Snapshot, CloudFormation creates a snapshot of the resource before deleting it.
* Point-in-time recovery (PITR) is the process of restoring a database to the state it was in at a specified date and time.
* An in-place upgrade involves performing application updates on live Amazon EC2 instances. A disposable upgrade, on the other hand, involves rolling out a new set of EC2 instances by terminating older instances.
* You can provide multiple IP addresses to a single EC2 instance. This can be easily achieved by using an Elastic Network Interface (ENI). An elastic network interface is a logical networking component in a VPC that represents a virtual network card.
* Lightweight Directory Access Protocol (LDAP) is a standard communications protocol used to read and write data to and from Active Directory. You can manage your user identities in an external system outside of AWS and grant users who sign in from those systems access to perform AWS tasks and access your AWS resources. The distinction is where the external system resides—in your data center or an external third party on the web.
* For enterprise identity federation, you can authenticate users in your organization's network, and then provide those users access to AWS without creating new AWS identities for them and requiring them to sign in with a separate user name and password. This is known as the single sign-on (SSO) approach to temporary access. AWS STS supports open standards like Security Assertion Markup Language (SAML) 2.0, with which you can use Microsoft AD FS to leverage your Microsoft Active Directory.
* You share resources in one account with users in a different account. By setting up cross-account access in this way, you don't need to create individual IAM users in each account. In addition, users don't have to sign out of one account and sign into another in order to access resources that are in different AWS accounts.
* Amazon CloudSearch is a managed service in the AWS Cloud that makes it simple and cost-effective to set up, manage, and scale a search solution for your website or application. Amazon CloudSearch supports 34 languages and popular search features such as highlighting, autocomplete, and geospatial search.
* Use AWS Application Discovery Service to gather information about the running virtual machines and running applications inside the servers. It helps enterprise customers plan migration projects by gathering information about their on-premises data centers.
* Use AWS Migration Hub to discover and track the status of the application migration across AWS and partner solutions.
* Use the AWS Cloud Adoption Readiness Tool (CART) to generate a migration assessment report to identify gaps in organizational skills and processes.
* In AWS Storage Gateway, your iSCSI initiators connect to your volumes as iSCSI targets. Storage Gateway uses Challenge-Handshake Authentication Protocol (CHAP) to authenticate iSCSI and initiator connections. CHAP provides protection against playback attacks by requiring authentication to access storage volume targets.
* AWS Transit Gateway is a highly available and scalable service used to consolidate the AWS VPC routing configuration for a region with a hub-and-spoke architecture. Each spoke VPC only needs to connect to the Transit Gateway to gain access to other connected VPCs. Transit Gateway across different regions can peer with each other to enable VPC communications across regions. With a large number of VPCs, Transit Gateway provides simpler VPC-to-VPC communication management over VPC Peering.
* Transit Gateway enables customers to connect thousands of VPCs. You can attach all your hybrid connectivity (VPN and Direct Connect connections) to a single Transit Gateway— consolidating and controlling your organization's entire AWS routing configuration in one place. 
* If you have a VPC peered with multiple VPCs that have overlapping or matching CIDR blocks, ensure that your route tables are configured to avoid sending response traffic from your VPC to the incorrect VPC. AWS currently does not support unicast reverse path forwarding in VPC peering connections that checks the source IP of packets and routes reply packets back to the source. 
* One of the major ways that you can improve the performance of an AWS Snowball Edge device is to speed up the transfer of data going to and from a device. In general, you can improve the transfer speed from your data source to the device in the following ways. The following list is ordered from largest to smallest positive impact on performance:
  * Perform multiple write operations at one time – To do this, run each command from multiple terminal windows on a computer with a network connection to a single AWS Snowball Edge device.
Transfer small files in batches – Each copy operation has some overhead because of encryption. To speed up the process, batch files together in a single archive. When you batch files together, they can be auto-extracted when they are imported into Amazon S3.
  * Write from multiple computers – A single AWS Snowball Edge device can be connected to many computers on a network. Each computer can connect to any of the three network interfaces at once.
  * Don't perform other operations on files during transfer – Renaming files during transfer, changing their metadata, or writing data to the files during a copy operation has a negative impact on transfer performance. AWS recommends that your files remain in a static state while you transfer them.
  * Reduce local network use – Your AWS Snowball Edge device communicates across your local network. So you can improve data transfer speeds by reducing other local network traffic between the AWS Snowball Edge device, the switch it's connected to, and the computer that hosts your data source.
  * Eliminate unnecessary hops – AWS recommends that you set up your AWS Snowball Edge device, your data source, and the computer running the terminal connection between them so that they're the only machines communicating across a single switch. Doing so can improve data transfer speeds.  
* Concurrency is the number of requests that your function is serving at any given time. When your function is invoked, Lambda allocates an instance of it to process the event. When the function code finishes running, it can handle another request. If the function is invoked again while a request is still being processed, another instance is allocated, which increases the function's concurrency. Concurrency is subject to a Regional quota that is shared by all functions in a Region.
* Amazon Macie is a security service that uses machine learning to automatically discover, classify, and protect sensitive data in AWS. Amazon Macie recognizes sensitive data such as personally identifiable information (PII) or intellectual property. 
* SSE-S3 provides strong multi-factor encryption in which each object is encrypted with a unique key. It also encrypts the key itself with a master key that it rotates regularly.
* Elastic Fabric Adapter (EFA) is a network interface for Amazon EC2 instances that enables customers to run applications requiring high levels of inter-node communications at scale on AWS.
* Improve the storage performance by implementing Amazon FSx for Lustre instead of using Amazon EFS.
* If you use CMKs, you use AWS KMS via the AWS Management Console or AWS KMS APIs to centrally create CMKs, define the policies that control how CMKs can be used, and audit their usage to prove that they are being used correctly. You can use these CMKs to protect your data in Amazon S3 buckets. 
* Server-side encryption is about protecting data at rest. Using server-side encryption with customer-provided encryption keys (SSE-C) allows you to set your own encryption keys. With the encryption key you provide as part of your request, Amazon S3 manages both the encryption as it writes to disks, and decryption when you access your objects. Therefore, you don't need to maintain any code to perform data encryption and decryption. The only thing you do is manage the encryption keys you provide. For Amazon S3 REST API calls, you have to include the following HTTP Request Headers:
  * x-amz-server-side-encryption-customer-algorithm
  * x-amz-server-side-encryption-customer-key
  * x-amz-server-side-encryption-customer-key-MD5
  * For presigned URLs, you should specify the algorithm using the x-amz-server-side-encryption-customer-algorithm request header.
* When you attach an SCP to your organization root or an OU, the SCP limits permissions for entities in member accounts. Even if a user is granted full administrator permissions with an IAM permission policy, any access that is not explicitly allowed or that is explicitly denied by the SCPs affecting that account is blocked.
* Consolidated billing has the following benefits:
  * One bill – You get one bill for multiple accounts.
  * Easy tracking – You can track the charges across multiple accounts and download the combined cost and usage data.
  * Combined usage – You can combine the usage across all accounts in the organization to share the volume pricing discounts, Reserved Instance discounts, and Savings Plans. This can result in a lower charge for your project, department, or company than with individual standalone accounts.
  * No extra fee – Consolidated billing is offered at no additional cost.
* You have a web application which is still under development but you want to enable access to it only for the employees via public Internet. In this scenario, you can implement an SSL VPN solution in which the employees can connect first and once they are authenticated, they will be granted access to the online portal. In this way, you can launch the web servers in the private subnet and still access it over the Internet via the VPN.
* After you create an organization and verify that you own the email address associated with the master account, you can invite existing AWS accounts to join your organization. When you invite an account, AWS Organizations sends an invitation to the account owner, who decides whether to accept or decline the invitation. You can use the AWS Organizations console to initiate and manage invitations that you send to other accounts. You can send an invitation to another account only from the master account of your organization.
* If you are the administrator of an AWS account, you also can accept or decline an invitation from an organization. If you accept, your account becomes a member of that organization. Your account can join only one organization, so if you receive multiple invitations to join, you can accept only one.
* API Gateway supports multiple mechanisms for controlling and managing access to your API.
You can use the following mechanisms for authentication and authorization:
  * Resource policies let you create resource-based policies to allow or deny access to your APIs and methods from specified source IP addresses or VPC endpoints.
  * Standard AWS IAM roles and policies offer flexible and robust access controls that can be applied to an entire API or individual methods. IAM roles and policies can be used for controlling who can create and manage your APIs, as well as who can invoke them.
  * IAM tags can be used together with IAM policies to control access.
  * Endpoint policies for interface VPC endpoints allow you to attach IAM resource policies to interface VPC endpoints to improve the security of your private APIs.
  * Lambda authorizers are Lambda functions that control access to REST API methods using bearer token authentication—as well as information described by headers, paths, query strings, stage variables, or context variables request parameters. Lambda authorizers are used to control who can invoke REST API methods.
  * Amazon Cognito user pools let you create customizable authentication and authorization solutions for your REST APIs. Amazon Cognito user pools are used to control who can invoke REST API methods.
* You can use Amazon CloudFront to improve the performance of your Amazon S3 website. CloudFront makes your website files (such as HTML, images, and video) available from data centers around the world (known as edge locations). When a visitor requests a file from your website, CloudFront automatically redirects the request to a copy of the file at the nearest edge location. This results in faster download times than if the visitor had requested the content from a data center that is located farther away.
* Amazon AppStream 2.0 is a fully managed application streaming service. You centrally manage your desktop applications on AppStream 2.0 and securely deliver them to any computer. You can easily scale to any number of users across the globe without acquiring, provisioning, and operating hardware or infrastructure.
* If you configure CloudFront to cache based on query string parameters, you can improve caching if you do the following:
  * Configure CloudFront to forward only the query string parameters for which your origin will return unique objects.
  * Use the same case (uppercase or lowercase) for all instances of the same parameter.
* SNI Custom SSL relies on the SNI extension of the Transport Layer Security protocol, which allows multiple domains to serve SSL traffic over the same IP address by including the hostname which the viewers are trying to connect to.
You can host multiple TLS secured applications, each with its own TLS certificate, behind a single load balancer. In order to use SNI, all you need to do is bind multiple certificates to the same secure listener on your load balancer. ALB will automatically choose the optimal TLS certificate for each client. These features are provided at no additional charge.
* After you've created your VPC, you further expand your network by associating one to utmost 4 secondary CIDR blocks to your VPC.
* Only one virtual private gateway (VGW) can be attached to a VPC at a time.
* At times, you need to give third party access to your AWS resources (delegate access). One important aspect of this scenario is the External ID, optional information that you can use in an IAM role trust policy to designate who can assume the role.
To use an external ID, update a role trust policy with the external ID of your choice. Then, when someone uses the AWS CLI or AWS API to assume that role, they must provide the external ID.
* Since Direct Connect does not provide any redundancy for its connection, it is recommended to set up at least two connections for high availability. However, this setup is expensive as you will be charged for the two Direct Connect connections. Usually, the second connection is used only when the main connection fails which rarely happens.
To maintain high availability, but reduce the costs, you can use a single AWS Direct Connect to create a dedicated private connection from your data center network to your Amazon VPC, and then combine this connection with an AWS managed VPN connection to create an IPsec-encrypted connection as a backup connection. If the Direct Connect connection fails, you still have a managed VPN to connect to your Amazon VPC, albeit with a slower connection. This will suffice until your Direct Connect connection is restored.
* An IAM role is an IAM identity that you can create in your account that has specific permissions. An IAM role is similar to an IAM user, in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it. Also, a role does not have standard long-term credentials such as a password or access keys associated with it. Instead, when you assume a role, it provides you with temporary security credentials for your role session. To delegate permission to access a resource, you create an IAM role in the trusting account that has two policies attached:
  * The permissions policy grants the user of the role the needed permissions to carry out the intended tasks on the resource.
  * The trust policy specifies which trusted account members are allowed to assume the role.
* Using roles to grant permissions to applications that run on EC2 instances requires a bit of extra configuration. An application running on an EC2 instance is abstracted from AWS by the virtualized operating system. Because of this extra separation, an additional step is needed to assign an AWS role and its associated permissions to an EC2 instance and make them available to its applications. This extra step is the creation of an instance profile that is attached to the instance.
* AWS Cloud Development Kit (AWS CDK) is a software development framework for defining cloud infrastructure in code and provisioning it through AWS CloudFormation.
* CloudEndure Migration is a block-level replication tool that simplifies the process of migrating applications from physical, virtual, and cloud-based servers to AWS. CloudEndure Migration supports any source infrastructure as long as it runs on x86 operating systems supported by Amazon Elastic Cloud Compute (EC2). This includes physical servers, P2V (virtual servers converted from physical), VMware, Hyper-V, and other cloud providers like Azure, GCP, IBM, or Oracle.
If your source environment includes bare metal servers, and you can install agents (more on agents in the next section), the recommendation is to use CloudEndure Migration.
* You can use workload management (WLM) to define multiple query queues and to route queries to the appropriate queues at runtime. Amazon Redshift workload management (WLM) enables users to flexibly manage priorities within workloads so that short, fast-running queries won't get stuck behind long-running queries.
* RAID 1 is recommended when you need fault tolerance for your EBS volumes.
* An SCP does not grant any permissions. Instead, SCPs are JSON policies that specify the maximum permissions for an organization or organizational unit (OU). The SCP limits permissions for entities in member accounts, including each AWS account root user.
* You can set up replication between an Amazon RDS MySQL (or MariaDB DB instance) that is running in AWS and a MySQL (or MariaDB instance) to your on-premises data center. Replication to an instance of MySQL running external to Amazon RDS is only supported during the time it takes to export a database from a MySQL DB instance.
* Redis is mostly a single-threaded server. It is not designed to benefit from multiple CPU cores unlike Memcached, however, you can launch several Redis instances to scale out on several cores if needed. Memcached is a more suitable choice. 
* It's a best practice that you upload SSL certificates to AWS Certificate Manager (ACM). If you're using certificate algorithms and key sizes that aren't currently supported by ACM or the associated AWS resources, then you can also upload an SSL certificate to IAM using AWS Command Line Interface (AWS CLI).
* Amazon Mechanical Turk (MTurk) is a crowdsourcing marketplace that makes it easier for individuals and businesses to outsource their processes and jobs to a distributed workforce who can perform these tasks virtually. 
* EC2Rescue can help you diagnose and troubleshoot problems on Amazon EC2 Linux and Windows Server instances. You can run the tool manually or you can run the tool automatically by using Systems Manager Automation and the AWSSupport-ExecuteEC2Rescue document. 
* Amazon WorkDocs is a fully managed, secure content creation, storage, and collaboration service. With Amazon WorkDocs, you can easily create, edit, and share content, and because it’s stored centrally on AWS, access it from anywhere on any device. Amazon WorkDocs makes it easy to collaborate with others, and lets you easily share content, provide rich feedback, and collaboratively edit documents. You can use Amazon WorkDocs to retire legacy file share infrastructure by moving file shares to the cloud. Amazon WorkDocs lets you integrate with your existing systems, and offers a rich API so that you can develop your own content-rich applications. Amazon WorkDocs is built on AWS, where your content is secured on the world's largest cloud infrastructure.
* AWS AppSync is a fully managed service that makes it easy to develop GraphQL APIs by handling the heavy lifting of securely connecting to data sources like Amazon DynamoDB, Lambda, and more. Adding caches to improve performance, subscriptions to support real-time updates, and client-side data stores that keep offline clients in sync are just as easy. Once deployed, AWS AppSync automatically scales your GraphQL API execution engine up and down to meet API request volumes.
* You can change the placement group for an instance in any of the following ways:
  * Move an existing instance to a placement group
  * Move an instance from one placement group to another
  * Remove an instance from a placement group
Before you move or remove the instance, the instance must be in the stopped state. You can move or remove an instance using the AWS CLI or an AWS SDK.