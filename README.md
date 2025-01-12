# Static-Website-Hosting-in-S3

### Prerequisites
- AWS Account

### Steps
- First, logged in the AWS Console. Then, Search S3 and click the S3 service.
- It will show the S3 service page. After, click **Create Bucket**.

![image](https://github.com/user-attachments/assets/6c204679-ecd6-4e0c-8bc3-a4587e59fc4f)

- Furthermore, type the **bucket name**. The bucket name should be unique.
- And use the default settings click **Create Bucket**.
- Then, click your bucket and upload your static website code by click the **Upload** button.

![image](https://github.com/user-attachments/assets/213018ef-95cb-47bf-afa2-da49f07ef60f)

- After, choose your bucket and select **Properties**. Scroll down and you can able to see **Static Website Hosting**.
- Then, click edit in the static website hosting. And **enable** the static website hosting. After, type your home page html file in the **Index Document** and save the changes.

![image](https://github.com/user-attachments/assets/0761df02-4d42-4326-9796-825fe648ef3e)

- In default, the S3 buckets are in private. So, you need allow the public access to access your static website.
- To make the bucket public select the **Permissions** of the bucket.

![image](https://github.com/user-attachments/assets/aaa614fb-b480-4ada-a196-1470f19e06d2)

- Afterwards, choose edit in the **Block public access** and unchecked the checkbox. Then, save the changes.
- Under the Block public access you can able to see **Bucket Policy**. Edit the Bucket Policy.

![image](https://github.com/user-attachments/assets/7ac00782-3177-4b6a-b5eb-172dc7f6d223)

- Copy the following policy and in the **Your Bucket Name** type your bucket name. Then, save the changes.

```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "Statement1",
			"Principal": "*",
			"Effect": "Allow",
			"Action": [
				"s3:GetObject"
			],
			"Resource": [
				"arn:aws:s3:::{Your Bucket Name}/*"
			]
		}
	]
}
```

- In the bucket properties tab you can see the **Bucket website endpoint** in static website hosting. Click the endpoint now you can see your static website in the browser.

![image](https://github.com/user-attachments/assets/202a4110-d8a6-4785-841a-5a0eda37b3aa)

- Now, your static website available in the internet. Anyone, can see your website using this endpoint.
