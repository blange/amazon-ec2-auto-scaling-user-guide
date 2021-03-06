# Launch templates<a name="LaunchTemplates"></a>

A launch template is similar to a [launch configuration](LaunchConfiguration.md), in that it specifies instance configuration information\. Included are the ID of the Amazon Machine Image \(AMI\), the instance type, a key pair, security groups, and the other parameters that you use to launch EC2 instances\. However, defining a launch template instead of a launch configuration allows you to have multiple versions of a template\. With versioning, you can create a subset of the full set of parameters and then reuse it to create other templates or template versions\. For example, you can create a default template that defines common configuration parameters and allow the other parameters to be specified as part of another version of the same template\. 

We recommend that you create Auto Scaling groups from launch templates to ensure that you're accessing the latest features and improvements\. If you plan to continue to use launch configurations with Amazon EC2 Auto Scaling, be aware that not all Auto Scaling group features are available\. For example, you cannot create an Auto Scaling group that launches both Spot and On\-Demand Instances or that specifies multiple instance types or multiple launch templates\. You must use a launch template to configure these features\. For more information, see [Auto Scaling groups with multiple instance types and purchase options](asg-purchase-options.md)\.

In addition to the features of Amazon EC2 Auto Scaling that you can configure by using launch templates, launch templates enable you to use newer features of Amazon EC2\. This includes the current generation of EBS volume types \(gp3 and io2\), EBS volume tagging, [T2 Unlimited instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-performance-instances-unlimited-mode-concepts.html), and [Dedicated Hosts](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html), to name a few\. Dedicated Hosts are physical servers with EC2 instance capacity that are dedicated to your use\. While Amazon EC2 [Dedicated Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-instance.html) also run on dedicated hardware, the advantage of using Dedicated Hosts over Dedicated Instances is that you can bring eligible software licenses from external vendors and use them on EC2 instances\. 

If you currently use launch configurations, you can specify a launch template when you update an Auto Scaling group that was created using a launch configuration\. 

To create a launch template to use with an Auto Scaling group, create the template from scratch, create a new version of an existing template, or copy the parameters from a launch configuration, running instance, or other template\. 

When you create or update an Auto Scaling group with a launch template, you must have sufficient permissions\. For more information, see [Launch template support](ec2-auto-scaling-launch-template-permissions.md)\.

The following topics describe the most common procedures for creating and working with launch templates for use with your Auto Scaling groups\. For more information about launch templates, see the [Launching an instance from a launch template](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html) section of the *Amazon EC2 User Guide for Linux Instances*\. 

**Topics**
+ [Creating a launch template for an Auto Scaling group](create-launch-template.md)
+ [Copying a launch configuration to a launch template](copy-launch-config.md)
+ [Replacing a launch configuration with a launch template](replace-launch-config.md)
+ [Examples for creating and managing launch templates with the AWS Command Line Interface \(AWS CLI\)](examples-launch-templates-aws-cli.md)