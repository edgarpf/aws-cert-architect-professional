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