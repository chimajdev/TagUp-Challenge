# TagUp-Challenge

You can create an s3 bucket from your EC2 instance, and before you do that

1. You will need to make sure that you create a user that has s3 Administrative previlege because using "aws configure" and creating a ".aws" credential file inside the ec2 instance will likely expose your access key ID and secret access key to hackers, but by adding the user to an s3 Admin Role/Policy and bucket policy allows the user to create and access s3 buckets securely without requiring them to include those sensitive information.

2. You will need to provide a region name, give the command "aws configure", hit enter two times and then enter a region name (us-east-1, us-east-2 etc).

3. Then to check if you can use aws cli client, you should give the test command "aws s3 ls" this command is used to check for the list of s3 buckets accessible to the user. If this steps does not work, contact your administrator to make sure you've been assigned an Admin Access for s3.

4. After giving the command "aws s3 ls" you should be able to view the list of buckets accessible to you. If this is a new user

5. To create a new bucket, you will need to give the command: "aws s3 mb s3://(bucketname)". This should return a "make_bucket: (bucketname)"
Note: S3 bucket names are universal so if your chosen bucket name is taken, you make a new one. S3 buckets are private by default

6. To list all the objects from the (bucketname) in a JSON format, you will need to use "s3api". Give this command: "aws s3api list-objects --bucket (bucketname)" This command will list the Bucket name, Creation date, Number of files, Total Size and the last modified date of the most recent file.
