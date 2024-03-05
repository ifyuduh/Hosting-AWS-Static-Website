# How-to-host-an-AWS-Static-Website
My learnings about hosting an AWS Static Website

![alt text](./images/Amazon%20S3%20Logo.png)
# Introduction

A simple step by step guide to creating an AWS S3 Static Website .

## Definition of terms
**Amazon S3** (Simple Storage Service) is a highly scalable cloud storage service provided by Amazon Web Services (AWS). It is designed to store and retrieve any amount of data from anywhere on the web..

**Bucket** is a container for storing objects on AWS S3.

**Bucket Policy** are a set of rules ,instructions or permissions that you can attach to an Amazon S3 bucket to control who can do what with the objects (files) stored in that bucket. 

**Create an S3 bucket using the AWS console and upload the attached index.html file**

**Step 1:** Login to your AWS console using your IAM username and password, by visiting [aws.com](https://aws.amazon.com) selecting sign in to console.

![alt text](./images/IAM%20User%20sign-in.png)

**Step 2:** Type "S3" into the search bar located at the top of the screen to locate and choose the S3 user console..

![alt text](./images/S3%20User%20console%20.png)

 **Step 3:** Click Create Bucket, then you select a region from the drop down menu, type in a unique Bucket Name for your bucket.

 ![alt text](./images/Click%20create%20bucket.png)
 ![alt text](./images/type%20a%20unique%20bucket%20name%20.png)

 **Step 4:** Object Ownership - Click on ACLs enabled, then give public access by unchecking the box that says Block all public access and check the warning box to acknowledge that you want to make the objects in the bucket public.

 ![alt text](./images/Enable%20ACLs%20on%20object%20ownership.png)

 **Step 5:** Allow public access by unchecking the box that says block all public access as the website needs to be accessible to everyone and check the warning box to acknowledge that you are granting public access to the objects.

![alt text](./images/Block%20all%20public%20access.png)


**Step 6:** Leave all other settings as default then click create bucket.

![alt text](./images/Select%20create%20bucket.png)

**Step 7:** Select the just created bucket from the general purpose bucket 
![alt text](./images/General%20Purpose%20bucket.png)

**Step 8** You upload and then add file

![alt text](./images/Upload%20.png)  Select Upload
![alt text](./images/Files%20and%20folder.png)
![alt text](./images/files%20and%20folder%202.png)
![alt text](./images/files%20and%20folder%203.png)

![alt text](./images/object%20uploaded%202.png)

## Modify the S3 Bucket

**Step 1** You should already be in your bucket if not select your just created bucket from the general purpose buckets and then select properties. Then in the properties tab scroll to the bottom you will see the section Static Website Hosting, you select edit to enable static website hosting

![alt text](./images/Properties.png)

![alt text](./images/Static%20website%20enable%201.png)

**Step 2** Once you select Edit you will select Enable for Static Website Hosting. You will also need to type in your Index Document you uploaded previously this is the default/home page for your website. Then you select save changes.

![alt text](./images/Static%20website%20enable%202.png)

![alt text](./images/Save%20changes.png)

 Static Website Hosting is now Enabled and it should also show the website we added in index document. if you try to access the website from the link it will not work but instead will give you an error message of 403 Forbidden on the webpage, we will be fixing that in our next steps.

 ![alt text](./images/static%20website%20enable%203.png)

 **Step 3** Still inside your created buckey you will select the Permissions tab.

![alt text](./images/Permissions%20tab.png)

**Step 4:** Scroll down to the Bucket policy section , there should be no policy displayed

![alt text](./images/Bucket%20policy.png)

Select Edit to add a bucket policy, then select Policy Generator(this will help you to write the necessary code to make your bucket public).

![alt text](./images/Edit%20bucket%20policy.png)

**Step 5** Within the Policy Generator, select Type of Policy as S3 Bucket Policy, Allow Effect, in the Principal add a * this basically allows anyone to get the object in the bucket.

![alt text](./images/Policy%20generator%201.png)

In Actions, you will select from the drop down GetObject.

![alt text](./images/Actions.png)

For the Amazon Resource Name (ARN), you will have to go back to the Edit Bucket Policy screen and copy the Bucket ARN provided.

![alt text](./images/ARN.png)

Click the Policy Generator again then paste the ARN in the Amazon Resource Name box. At the end of the name you will need to type /*. The /* is to enable the GetObject action to retrieve the object in ARN box from the bucket. Then you select Add Statement. Then you click the button Generate Policy.

![alt text](./images/Add%20statement.png)

![alt text](./images/Generate%20policy.png)

Then you copy the policy it generates. 

![alt text](./images/Policy.png)

**Step 6:** Go back to the Edit Bucket Policy screen and paste the policyy generated (this is also a code) in the Policy window and select save changes.

![alt text](./images/Edit%20bucket%20policy%20(2).png)

**Step 7** Click the permissions tab of the bucket and it should now be showing Access as Public.

![alt text](./images/Permissions%20showing%20public.png)

 ## **Verify internet access using the Bucket website endpoint and the Object URL.**

 **Step 1:** To access the Bucket Website Endpoint select the Properties tab of the Bucket. Then scroll to the bottom to the Static Website Hosting tab and you will see the Website Endpoint.

 ![alt text](./images/Bucket%20webiste%20endpoint.png)

![alt text](./images/Bucket%20website%20endpoint%202.png)

**Step 2:** Click the endpoint and the website will appear. 

![alt text](./images/Static%20Website.png)






