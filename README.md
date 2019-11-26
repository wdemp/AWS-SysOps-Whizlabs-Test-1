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
Whizlabs Answer: According to the answer from Whizlabs: If you have an existing VPC that supports IPv4 only, and resources in your subnet that are configured to use IPv4 only, you can enable IPv6 support for your VPC and resources. Your VPC can operate in dual-stack mode — your resources can communicate over IPv4, or IPv6, or both. IPv4 and IPv6 communication are independent of each other.
