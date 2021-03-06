# AWS Config ConfigRule Source<a name="aws-properties-config-configrule-source"></a>

`Source` is a property of the [AWS::Config::ConfigRule](aws-resource-config-configrule.md) resource that specifies the rule owner, the rule identifier, and the events that trigger an AWS Config evaluation of your AWS resources\.

## Syntax<a name="w3ab2c21c14d456b5"></a>

### JSON<a name="aws-properties-config-configrule-source-syntax.json"></a>

```
{
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-owner)" : String,
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-sourcedetails)" : [ SourceDetail, ... ],
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-sourceidentifier)" : String
}
```

### YAML<a name="aws-properties-config-configrule-source-syntax.yaml"></a>

```
[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-owner): String
[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-sourcedetails):
  - SourceDetail
[[ERROR] BAD/MISSING LINK TEXT](#cfn-config-configrule-source-sourceidentifier): String
```

## Properties<a name="w3ab2c21c14d456b7"></a>

`Owner`  
Indicates who owns and manages the AWS Config rule\. For valid values, see the [Source](http://docs.aws.amazon.com/config/latest/APIReference/API_Source.html) data type in the *AWS Config API Reference*\.  
*Required: *Yes  
*Type*: String

`SourceDetails`  
Provides the source and type of event that triggers AWS Config to evaluate your AWS resources\.  
*Required: *No  
*Type*: List of [AWS Config ConfigRule SourceDetails](aws-properties-config-configrule-source-sourcedetails.md)

`SourceIdentifier`  
For AWS managed rules, the identifier of the rule\. For a list of identifiers, see [AWS Managed Rules](http://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html) in the *AWS Config Developer Guide*\.  
For customer managed rules, the Amazon Resource Name \(ARN\) of the rule's Lambda function\.  
*Required: *Yes  
*Type*: String