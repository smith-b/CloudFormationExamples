prerequisites:
    These templates assume you have an EC2 KeyPair to assign to the EC2 instances in the auto scaling group. You can reference this AWS tutorial if you do not already have one, https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair

The public-private-2az.json template will create a VPC, two public and two private subnets across 2 availability zones, an internet gateway and a NAT gateway. This stack will also export values that can be used for cross stack referencing

The loadbalanced-ha-asg-sample-ec2-app.json template will create an auto scaling group and launch configuration that bootstraps EC2 instances with different configuration packages according to the evaluation of the "Configuration" parameter. This stack will also create two security groups, an IAM role and instance profile to associate with EC2 instances in the auto scaling group, an application load balancer, listener, and target group.

There is a very small cost associated with creating these stacks. Review AWS service costs and use the following online calculator to identify a specific number according to your instance size, runtime, and traffic. https://calculator.s3.amazonaws.com/index.html