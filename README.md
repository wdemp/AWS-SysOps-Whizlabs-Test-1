# AWS-SysOps-Whizlabs-Test-1
Q&amp; A, Analysis and Description ofWrong Questions


Q: Your company currently has a VPC with EC2 Instances. A new instance being launched which will host an application that works on IPv6. You need to ensure that this instance can initiate traffic outgoing to the Internet.
At the same time, you need to ensure that no incoming connection can be initiated from the Internet on to the Instance. 
Which of the following would you add to the VPC for this requirement?

A: An egress only internet gateway: 
Wrong Answer: Attach a NAT Gateway
Reason it's Wrong: The reason my answer was wrong was because an egress only gateway is used for IPV6, while a NAT Gateway would be used more for instances in a private subnet wnen used to communicate with the internet(whizlabs)
Reason why "Egress only Internet Gateway" is correct: An Egrees only Inernet Gateway is the best answer to this question for a few reasons. The first reason is the question explicitly states that IPV6 needs to be used on the instance and can initiate outgoing traffic to the internet. An egrees only internet gateway is designed specifically for IPV6. The other reason is that
since in this scenario you want to make sure that no other traffic is coming in. An engrees only Internet Gateway can ensure that your instance communicates with the proper traffic you want it to. 


Q2: Your company currently has a VPC with EC2 Instances. A new instance being launched which will host an application that works on IPv6. Which of the following pre-requisite needs to be followed to ensure that the new Instance can communicate over IPv6?
My Answer: Attach an Egress -only Internet Gateway
Real Answer: Ensure your VPC works in Dual Stack Mode
My Reasoning: I didn't really understand the question that well and still have a lot of problems with some of the terminology.
Whizlabs Answer: According to the answer from Whizlabs: "If you have an existing VPC that supports IPv4 only, and resources in your subnet that are configured to use IPv4 only, you can enable IPv6 support for your VPC and resources. Your VPC can operate in dual-stack mode — your resources can communicate over IPv4, or IPv6, or both. IPv4 and IPv6 communication are independent of each other." The reason all the other questions were wrong was because the question has no mention of the instances needing to connect to the internet.

Q3: Your development team has currently made changes to an application which is hosted in AWS. Currently the application is in Production and Route 53 is being used as the DNS service. The new version of the application has undergone testing and now needs to be promoted to a separate environment. They need an initial set of traffic to be directed to the new version of the application for testing, before the final cutover can be made. Which of the following would you implement?

My Answer: 2 resource records based on the Simple Routing Policy
Reason its Wrong: The question makes no mention of needing any routing policy, although it might slightly hint at it. I'm still not very good at this section.

Real Answer: 2 resources based on the Weighted Policy
The Reason: "Weighted routing lets you associate multiple resources with a single domain name (example.com) or subdomain name (acme.example.com) and choose how much traffic is routed to each resource. This can be useful for a variety of purposes, including load balancing and testing new versions of software."
Analysis: Upon looking back at the question and the answer this is making more sense. The question mentions " a seperate environment" being needed. This makes me think back to what weighted policy means. For the most part is has to deal with when to emphasis something more in the policy; be it a routing poicy or whatever is needed in the scenario.

Q4: A company is planning for hosting a 3-tier application onto AWS. The presentation layer is hosted on a set of web servers and are placed in a public subnet. Application layer hosted on 2 EC2 instances, and Oracle database servers, hosted on EC2 instances are placed in a private subnet. You need to ensure that all traffic has been evenly distributed. Also, you need to ensure that database servers are not accessible on the Internet.
Which of the following 2 configurations you will propose to implement?

Answer I put: It turns out that I got half of this question correct since it involved selecting 2 answers. However wrong is wrong on a practice test. The second half of the question was wrong because "incorrect since it is mentioned that database servers should not be accessible to the Internet, so these need to be internal load balancers" (whizlabs answer) The other correct answer was "create an internal load balancer for the database layer"

Correct Answers: "create an internal load balaner for the database layer" and  "create an internal load balancer for the web server" 

Q8: You’re planning on allowing an Administrator to setup an EC2 Instance. This EC2 Instance will host an application that would need access to a DynamoDB table. Which of the following policy permissions are required to ensure that from a security perspective this implementation can be carried out? Choose 2 answers from the options given below.

My Answer: I put down the 2 answers that were completely wrong. This was due to not fully understanding the question and some of the terminology.
Real Answers: "A trust policy that allows the EC2 Instance to assume a role" and  "An IAM policy that allows the user to pass on a role." 
Analysis: The mention of IAM roles makes it more obvious that this was half of the answer. You cannot really do much of anything on AWS without having the proper persmissions established for the servce prior. Having permission granted prior by the admin will ensure the user can perform his or her duties without them being hindered. A Trust policy must also be used in this scenario because the policy will allow the service to use the role and permissions assigned to it.

Q9: You are working as a SysOps administrator for a legal organisation. All contractual documents need to be archived for 5 years without modifications. You are planning to store these documents in Amazon S3 Glacier with Vault lock.  Initiate Vault Lock is initiated to add controls which will deny any user to make changes in these documents. Which of the following additional actions need to be initiated to complete Amazon S3 Glacier Vault lock policy?

My Answer: "Initiate Complete Vault Lock Operation within 12 hours using Lock ID generated during initiative Vault Lock" I did not understand this question at all or most of the terms in it.
Real Answer: Initiate Complete Vault Lock operation within 24 hours using Lock ID generated during Initiate Lock Vault

Whizlabs answer: "A Vault lock policy can be used to lock vault for any future changes. Attaching a Vault lock policy is a 2-step process. First an Initiate Vault Lock is called which will attach a vault lock policy to the vault & returns a unique lock ID. Post verification , a Complete Vault Lock needs to  be initiated within 24 hours using lock ID generated from Initiate Vault Lock. If a Complete Vault is not initiated within 24 hours , vault lock policy is removed."

Q11: Your company is planning on setting up multiple accounts in AWS. The IT Security department has a requirement to ensure that certain services and actions are not allowed across all accounts. How would you achieve this in the most EFFECTIVE way possible?
My Answer: Apply and IAM policy per account and apply them accordingly.
Real Answer: Use AWS Organizations and Service Control Policies 
Reason it's Wrong: I know enough to realize this was due to not reading throughly enough and not paying attention. There is no other necessary sections to type out beyond this.

Q12:A financial firm is using Amazon S3 bucket to save all critical documents. Security Team requires a detailed logs for all users who would be accessing these buckets & actions performed by these users. As a SysOps administrator, you are planning to enable Amazon S3 Server Access Logs for all these buckets. Which of the following permission will require for logs to be delivered in target bucket “targetexample” ?
My Answer: Grant write permissions Log Delivery group on S3 Bucket "targetexample" using bucket policy
Real Answer: Grant write permissions Log Delivery group on S3 Bucket "taerget example" using bucket ACL
Whizlabs answer: Amazon S3 uploads access log files to target bucket using a special account, as Log Delivery group. This account should have write access on target bucket to save all logs. To grant access, bucket ACL is used  & not by bucket policy.

Q14:  he following policy has been set on a bucket

{

  "Version": "2012-10-17",

  "Id": "demopolicy",

  "Statement": [

    {

      "Sid": "IPAllow",

      "Effect": "Allow",

      "Principal": "*",

      "Action": "s3:*",

      "Resource": "arn:aws:s3:::demobucket/*",

      "Condition": {

         "IpAddress": {"aws:SourceIp": "54.240.143.0/24"},

         "NotIpAddress": {"aws:SourceIp": "54.240.143.188/32"}

      }

    }

  ]

}

What does this policy do?

My Answer: Ensure that clients in the range of 54.240.143.0/24 are denied access to all objects in the demobucket
Real Answer: Ensure that the clients with the IP address of 54.240.143.188 is denied access to the objects in the demobucket


Q15: You are working as a SysOps administrator for a large IT firm. After successful set-up of Systems Manager on EC2 instance across all regions, you are planning to set-up Systems Manager for 50  database servers deployed in corporate Data Centre. Which of the following actions are mandatory to complete Systems Manager set-up on these servers? (Select Four.)

Answers I chose: I got 3 out of the 4 correct.
Real Answers: Download and install SSM Agent on servers in Data Centre, Create an IAM Role to communicate with the Systems Manager service, Install a TLS certificate on servers in Data Centre, Create a managed instance activation for servers in Data Centres.
Q16: You are working as a SysOps Administrator for a large construction company. Last week there was an outage in few critical Production servers as third-party unauthorised software was installed on these servers.  As a SysOps Administrator, you have been asked to maintain a predefined state for all Instance in US-West-1 region. Which of the following can be used to perform this task?
My answer: Use state manager with Policy Document
Real Answer: Use State Manager with Command Document 
Analysis: I don't understand these terms yet.

Q17: A large multinational firm is using 3-tier application installed on EC2 instance in VPC. They are using Amazon GuardDuty for monitoring malicious activities & traffic patterns hitting web application. Initially they were using Amazon GuardDuty for master account in us-west-1 region which now has been expanded to other member accounts in the same region. One of the member account is observing a huge amount of traffic from an IP address accessing web application. Security lead for this member account is looking for detail activities from this IP address. Which of the following actions will meet this requirement ?
My Answer: Request users from member account to modify Threat list to include this IP address.
Real Answer: Request users from master account to modify Threat list to include this IP address.
Analysis: I need to go over more Guard Duty
