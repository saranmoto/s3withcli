# s3withcli
### Create, Copy, list files in S3 with CLI.

1. Download and install `AWS CLI` for windows. 

   *To download latest version of the AWS CLI, kindly visit: https://awscli.amazonaws.com/AWSCLIV2.msi*

   *For other OS, kindly visit: https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html*
2. Create a IAM User with `Programatic access`.
3. Attach existing policy `AmazonS3FullAccess` to user directly.
4. After creation, download your `access key and secret access key` (as .csv file).

   *For Step 2 to 4, kindly refer https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html*
5. Go to command prompt in windows and follow below steps.
6. >C:\Users\hp>**aws configure**

	 AWS Access Key ID [None]: **Your access key**	
	 
	 AWS Secret Access Key [None]: **Your secret access key**
	 
	 Default region name [None]: **Your region**
	 
	 Default output format [None]:
7. >C:\Users\hp>**aws s3 ls** 
   
   Output -> *Shows list of buckets in S3, currently no bucket* 
8. Create a bucket with below command.  

   >C:\Users\hp>aws s3 mb s3://**YourBucketName**

   Output -> *make_bucket: YourBucketName*
9. Copy local files to bucket with below cmd.
   
   >C:\Users\hp\Desktop\Saran>aws s3 cp **YourFile** s3://**YourBucketName**`
   
   Output -> *upload: .\\YourFile to s3://YourBucketName/YourFile*
   
   If you want to copy local files with diff name use below cmd.
   
   >C:\Users\hp\Desktop\Saran>aws s3 cp **YourFile** s3://**YourBucketName**/**YourName**
   
   Output -> *upload: .\\YourFile to s3://YourBucketName/YourName*
10. To make the file public
    
    >C:\Users\hp\Desktop\Saran>aws s3api put-object-acl --bucket **YourBucketName** --key **YourFile** --acl public-re
