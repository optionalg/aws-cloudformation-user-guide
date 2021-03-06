# Amazon S3 Bucket NotificationConfiguration<a name="aws-properties-s3-bucket-notificationconfig"></a>

Describes the notification configuration for an  AWS::S3::Bucket resource\.

**Note**  
If you create the target resource and related permissions in the same template, you might have a circular dependency\.  
For example, you might use the AWS::Lambda::Permission resource to grant the S3 bucket to invoke a Lambda function\. However, AWS CloudFormation can't create the S3 bucket until the bucket has permission to invoke the function \(AWS CloudFormation checks if the S3 bucket can invoke the function\)\. If you're using Refs to pass the bucket name, this leads to a circular dependency\.  
To avoid this dependency, you can create all resources without specifying the notification configuration\. Then, update the stack with a notification configuration\.

## Syntax<a name="w3ab2c21c14e1511b7"></a>

### JSON<a name="aws-properties-s3-bucket-notificationconfig-syntax.json"></a>

```
{
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-lambdaconfig)" : [ Lambda Configuration, ... ],
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-queueconfig)" : [ Queue Configuration, ... ],
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-topicconfig)" : [ Topic Configuration, ... ]
}
```

### YAML<a name="aws-properties-s3-bucket-notificationconfig-syntax.yaml"></a>

```
[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-lambdaconfig):
  - Lambda Configuration
[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-queueconfig):
  - Queue Configuration
[[ERROR] BAD/MISSING LINK TEXT](#cfn-s3-bucket-notificationconfig-topicconfig):
  - Topic Configuration
```

## Properties<a name="w3ab2c21c14e1511b9"></a>

`LambdaConfigurations`  
The AWS Lambda functions to invoke and the events for which to invoke the functions\.  
*Required: *No  
*Type*: [Amazon S3 Bucket LambdaConfiguration](aws-properties-s3-bucket-notificationconfig-lambdaconfig.md)

`QueueConfigurations`  
The Amazon Simple Queue Service queues to publish messages to and the events for which to publish messages\.  
*Required: *No  
*Type*: [Amazon S3 Bucket QueueConfiguration](aws-properties-s3-bucket-notificationconfig-queueconfig.md)

`TopicConfigurations`  
The topic to which notifications are sent and the events for which notification are generated\.  
*Required: *No  
*Type*: [Amazon S3 Bucket TopicConfiguration](aws-properties-s3-bucket-notificationconfig-topicconfig.md)