# AWS::EC2::InternetGateway<a name="aws-resource-ec2-internetgateway"></a>

Creates a new Internet gateway in your AWS account\. After creating the Internet gateway, you then attach it to a VPC\.


+ [Syntax](#aws-resource-ec2-internetgateway-syntax)
+ [Properties](#w3ab2c21c10d378b9)
+ [Return Values](#w3ab2c21c10d378c11)
+ [Example](#w3ab2c21c10d378c13)
+ [Related Information](#w3ab2c21c10d378c15)

## Syntax<a name="aws-resource-ec2-internetgateway-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-resource-ec2-internetgateway-syntax.json"></a>

```
{
   "Type" : "AWS::EC2::InternetGateway",
   "Properties" : {
      "Tags" : [ Resource Tag, ... ]
   }
}
```

### YAML<a name="aws-resource-ec2-internetgateway-syntax.yaml"></a>

```
Type: "AWS::EC2::InternetGateway"
Properties: 
  Tags:
    - Resource Tag
```

## Properties<a name="w3ab2c21c10d378b9"></a>

`Tags`  
An arbitrary set of tags \(key–value pairs\) for this resource\.  
*Required: *No  
*Type*:   
*Update requires*: No interruption

## Return Values<a name="w3ab2c21c10d378c11"></a>

### Ref<a name="w3ab2c21c10d378c11b2"></a>

When the logical ID of this resource is provided to the `Ref` intrinsic function, `Ref` returns the resource name\.

For more information about using the `Ref` function, see Ref\.

## Example<a name="w3ab2c21c10d378c13"></a>

### JSON<a name="aws-resource-ec2-internetgateway-example.json"></a>

```
{
   "AWSTemplateFormatVersion" : "2010-09-09",
   "Resources" : {
      "myInternetGateway" : {
         "Type" : "AWS::EC2::InternetGateway",
         "Properties" : {
            "Tags" : [ {"Key" : "foo", "Value" : "bar"}]
         }
      }
   }
}
```

### YAML<a name="aws-resource-ec2-internetgateway-example.yaml"></a>

```
AWSTemplateFormatVersion: '2010-09-09'
Resources:
  myInternetGateway:
    Type: "AWS::EC2::InternetGateway"
    Properties:
      Tags:
      - Key: foo
        Value: bar
```

## Related Information<a name="w3ab2c21c10d378c15"></a>

+ [CreateInternetGateway](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateInternetGateway.html) in the *Amazon EC2 API Reference*\.

+ Use the [AWS::EC2::VPCGatewayAttachment](aws-resource-ec2-vpc-gateway-attachment.md) resource to associate an Internet gateway with a VPC\.