# AWS::EMR::SecurityConfiguration<a name="aws-resource-emr-securityconfiguration"></a>

The `AWS::EMR::SecurityConfiguration` resource creates a security configuration that is stored in the Amazon EMR web service\. You can specify the security configuration when creating a cluster\. For more information, see [ Specifying Amazon EMR Encryption Options Using a Security Configuration](http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-encryption-enable-security-configuration.html) in the *Amazon EMR Release Guide*\.


+ [Syntax](#aws-resource-emr-securityconfiguration-syntax)
+ [Properties](#aws-resource-emr-securityconfiguration-properties)
+ [Return Values](#aws-resource-emr-securityconfiguration-returnvalues)
+ [Example](#aws-resource-emr-securityconfiguration-examples)

## Syntax<a name="aws-resource-emr-securityconfiguration-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-resource-emr-securityconfiguration-syntax.json"></a>

```
{
  "Type" : "AWS::EMR::SecurityConfiguration",
  "Properties" : {
    "[[ERROR] BAD/MISSING LINK TEXT](#cfn-emr-securityconfiguration-name)" : String,
    "[[ERROR] BAD/MISSING LINK TEXT](#cfn-emr-securityconfiguration-securityconfiguration)" : String
  }
}
```

### YAML<a name="aws-resource-emr-securityconfiguration-syntax.yaml"></a>

```
Type: "AWS::EMR::SecurityConfiguration"
Properties: 
  [[ERROR] BAD/MISSING LINK TEXT](#cfn-emr-securityconfiguration-name): String
  [[ERROR] BAD/MISSING LINK TEXT](#cfn-emr-securityconfiguration-securityconfiguration): String
```

## Properties<a name="aws-resource-emr-securityconfiguration-properties"></a>

For more information about each property, including constraints and valid values, see [CreateSecurityConfiguration](http://docs.aws.amazon.com/ElasticMapReduce/latest/API/API_CreateSecurityConfiguration.html) in the *Amazon EMR API Reference*\.

`Name`  
The name of the security configuration\. For a list of valid parameters for encryption settings, see [ AWS CLI Security Configuration JSON Reference](http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-encryption-enable-security-configuration.html#emr-encryption-cli-parameters) in the *Amazon EMR Release Guide*\.  
*Required: *No  
*Type*: String  
*Update requires*: Replacement

`SecurityConfiguration`  
The security configuration details in JSON format\.  
*Required: *Yes  
*Type*: String  
*Update requires*: Replacement

## Return Values<a name="aws-resource-emr-securityconfiguration-returnvalues"></a>

### Ref<a name="aws-resource-emr-securityconfiguration-ref"></a>

When the logical ID of this resource is provided to the `Ref` intrinsic function, `Ref` returns the security configuration name, such as `mySecurityConfiguration`\.

For more information about using the `Ref` function, see Ref\.

## Example<a name="aws-resource-emr-securityconfiguration-examples"></a>

### <a name="aws-resource-emr-securityconfiguration-example1"></a>

The following example enables both in\-transit data encryption and local disk encryption\. For additional encryption configuration examples, see [ Creating a Security Configuration Using the AWS CLI](http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-encryption-enable-security-configuration.html#emr-encryption-cli) in the *Amazon EMR Release Guide*\.

#### JSON<a name="aws-resource-emr-securityconfiguration-example1.json"></a>

```
{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Resources": {
        "securityConfiguration": {
            "Type": "AWS::EMR::SecurityConfiguration",
            "Properties": {
                "SecurityConfiguration": {
                    "EncryptionConfiguration": {
                        "EnableInTransitEncryption": true,
                        "EnableAtRestEncryption": true,
                        "InTransitEncryptionConfiguration": {
                            "TLSCertificateConfiguration": {
                                "CertificateProviderType": "PEM",
                                "S3Object": "arn:aws:s3:::MyConfigStore/artifacts/MyCerts.zip"
                            }
                        },
                        "AtRestEncryptionConfiguration": {
                            "S3EncryptionConfiguration": {
                                "EncryptionMode": "SSE-KMS",
                                "AwsKmsKey": "arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012"
                            },
                            "LocalDiskEncryptionConfiguration": {
                                "EncryptionKeyProviderType": "AwsKms",
                                "AwsKmsKey": "arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012"
                            }
                        }
                    }
                }
            }
        }
    }
}
```

#### YAML<a name="aws-resource-emr-securityconfiguration-example1.yaml"></a>

```
AWSTemplateFormatVersion: 2010-09-09
Resources:
  securityConfiguration:
    Type: 'AWS::EMR::SecurityConfiguration'
    Properties:
      SecurityConfiguration:
        EncryptionConfiguration:
          EnableInTransitEncryption: true
          EnableAtRestEncryption: true
          InTransitEncryptionConfiguration:
            TLSCertificateConfiguration:
              CertificateProviderType: PEM
              S3Object: 'arn:aws:s3:::MyConfigStore/artifacts/MyCerts.zip'
          AtRestEncryptionConfiguration:
            S3EncryptionConfiguration:
              EncryptionMode: SSE-KMS
              AwsKmsKey: >-
                arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
            LocalDiskEncryptionConfiguration:
              EncryptionKeyProviderType: AwsKms
              AwsKmsKey: >-
                arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
```