# Create an Amazon S3 bucket for Amazon MWAA<a name="mwaa-s3-bucket"></a>

This guide describes the steps create an Amazon S3 bucket to store your Apache Airflow Directed Acyclic Graphs \(DAGs\), custom plugins in a `plugins.zip` file, and Python dependencies in a `requirements.txt` file\. 

**Contents**
+ [Before you begin](#mwaa-s3-bucket-before)
+ [Create the bucket](#mwaa-s3-bucket-create)
+ [What's next?](#mwaa-s3-bucket-next-up)

## Before you begin<a name="mwaa-s3-bucket-before"></a>
+ The Amazon S3 bucket name can't be changed after you create the bucket\. To learn more, see [Rules for bucket naming](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html#bucketnamingrules) in the *Amazon Simple Storage Service Developer Guide*\.
+ An Amazon S3 bucket used for an Amazon MWAA environment must be configured to **Block all public access**, with **Bucket Versioning** enabled\.
+ An Amazon S3 bucket used for an Amazon MWAA environment must be located in the same AWS Region as an Amazon MWAA environment\. To view a list of AWS Regions for Amazon MWAA, see [Amazon MWAA regions](what-is-mwaa.md#regions-mwaa)\.

## Create the bucket<a name="mwaa-s3-bucket-create"></a>

This section describes the steps to create the Amazon S3 bucket for your environment\.

**To create a bucket**

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console\.aws\.amazon\.com/s3/](https://console.aws.amazon.com/s3/)\.

1. Choose **Create bucket**\.

1. In **Bucket name**, enter a DNS\-compliant name for your bucket\.

   The bucket name must:
   + Be unique across all of Amazon S3\.
   + Be between 3 and 63 characters long\.
   + Not contain uppercase characters\.
   + Start with a lowercase letter or number\.
**Important**  
Avoid including sensitive information, such as account numbers, in the bucket name\. The bucket name is visible in the URLs that point to the objects in the bucket\.

1. Choose an AWS Region in **Region**\. This must be the same AWS Region as your Amazon MWAA environment\. 

   We recommend choosing a region close to you to minimize latency and costs and address regulatory requirements\. 

1. Choose **Block all public access**\.

1. Choose **Enable** in **Bucket Versioning**\.

1. **Optional**\. Add tags to identify your Amazon S3 bucket in **Tags**\. 

1. **Optional**\. Choose **Enable** in **Server\-side encryption** to enable server\-side encryption for the bucket\. 

   If you choose to enable server\-side encryption, you must use the same encryption key for your Amazon S3 bucket and Amazon MWAA environment\.

1. **Optional** \- *Advanced settings*\. If you want to enable Amazon S3 Object Lock:

   1. Choose **Advanced settings**, **Enable**\.
**Important**  
Enabling Object Lock will permanently allow objects in this bucket to be locked\. To learn more, see [Locking Objects Using Amazon S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) in the *Amazon Simple Storage Service Developer Guide*\.

   1. Choose the acknowledgement\.

1. Choose **Create bucket**\.

## What's next?<a name="mwaa-s3-bucket-next-up"></a>
+ Learn how to create the required Amazon VPC network for an environment in [Create the VPC network](vpc-create.md)\.
+ Learn how to how to manage access permissions in [How do I set ACL bucket permissions?](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/set-bucket-permissions.html)
+ Learn how to delete a storage bucket in [How do I delete an S3 Bucket?](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/delete-bucket.html)\.