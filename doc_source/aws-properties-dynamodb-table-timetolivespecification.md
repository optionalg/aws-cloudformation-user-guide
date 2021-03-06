# Amazon DynamoDB Table TimeToLiveSpecification<a name="aws-properties-dynamodb-table-timetolivespecification"></a>

The `TimeToLiveSpecification` property specifies the Time to Live \(TTL\) settings for an [AWS::DynamoDB::Table](aws-resource-dynamodb-table.md) resource\. It is expressed as an attribute on the items in the table\. For more information, see [UpdateTimeToLive](http://docs.aws.amazon.com//amazondynamodb/latest/APIReference/API_UpdateTimeToLive.html) in the *Amazon DynamoDB API Reference*\.

## Syntax<a name="w3ab2c21c14d550b5"></a>

### JSON<a name="aws-properties-dynamodb-table-timetolivespecification-syntax.json"></a>

```
{
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-dynamodb-table-timetolivespecification-attributename)" : String,
  "[[ERROR] BAD/MISSING LINK TEXT](#cfn-dynamodb-table-timetolivespecification-enabled)" : Boolean
}
```

### YAML<a name="aws-properties-dynamodb-table-timetolivespecification-syntax.yaml"></a>

```
[[ERROR] BAD/MISSING LINK TEXT](#cfn-dynamodb-table-timetolivespecification-attributename): String
[[ERROR] BAD/MISSING LINK TEXT](#cfn-dynamodb-table-timetolivespecification-enabled): Boolean
```

## Properties<a name="w3ab2c21c14d550b7"></a>

`AttributeName`  
The name of the TTL attribute that stores the expiration time for items in the table\. The name can be 1–255 characters long, and has no character restrictions\.  
*Required: *Yes  
*Type*: String  
*Update requires*: No interruption

`Enabled`  
Indicates whether to enable \(by specifying `true`\) or disable \(by specifying `false`\) TTL on the table\.  
*Required: *Yes  
*Type*: Boolean  
*Update requires*: No interruption