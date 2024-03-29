# Introduction to Amazon S3

## Amazon S3 Overview:
Amazon S3 is storage for the internet, designed for web-scale and cloud-native computing. It seamlessly integrates with a wide range of AWS services, facilitating robust workloads.

## Simple Web Service Interface:
Amazon S3 offers a simple web service interface for storing and retrieving any amount of data from anywhere on the web. It utilizes standards-based REST APIs compatible with any internet-development toolkit.

## Features and Capabilities:
- Data is stored as objects within buckets, supporting various use cases, cost efficiencies, security, and compliance requirements.
- Each object can be up to 5 terabytes in size.
- Objects can be accessed through S3 Access Points or directly via the bucket hostname.

## Amazon S3 features include the following capabilities:
- Appending metadata tags to objects
- Moving and storing data across different S3 storage classes
- Configuring and enforcing data access controls
- Securing data against unauthorized users
- Running big data analytics
- Monitoring data at the object or bucket levels
- Viewing storage usage and activity trends across your organization

## Top-level Amazon S3 features:
- Increase agility.
- Accelerate innovation.
- Strengthen security.
- Reduce costs.

## How to create an S3 bucket:
1. **Sign in to AWS Console:**
   - Make sure you have an AWS account. Go to the AWS Management Console, sign in, and navigate to the S3 service.
   
2. **Access S3 Service:**
   - Click on the "Services" dropdown at the top left corner, select "S3" under "Storage."
   
3. **Create a Bucket:**
   - Once in the S3 console, click the "Create bucket" button.
   
4. **Configure Bucket:**
   - **Name and Region:**
     - Enter a unique and globally unique name for your bucket.
     - Choose a region for your bucket. It's a good practice to select a region closest to your users for better performance.
   - **Configure options (Optional):**
     - You can set additional options like versioning, logging, tags, etc. These are optional and can be configured based on your needs.
   - **Set permissions:**
     - Choose who can access your bucket. You can configure permissions and access control settings here.
   - **Review:**
     - Review your configuration and make sure everything is set as per your requirements.
   
5. **Create the Bucket:**
   - Click the "Create bucket" button.

*Your S3 bucket is now created, and you can start using it to store objects (files) and configure additional settings as needed.*

## How to make your bucket object public, use the policy generator, and allow an object to be public:

### Allow object to be public:
- Navigate to Permission -> Block public access -> edit -> uncheck that -> save change -> confirm.

### Policy generator:
1. **Navigate to permission:**
   - Slide down -> Bucket Policy -> Edit.
   
2. **Click on the policy generator.**

3. **Step 1:**
   - Select Policy Type -> select in dropdown -> S3 bucket policy.
   
4. **Step 2: Add Statement:**
   - Effect -> Allow
   - Principal -> *
   - Action -> getObject
   - Amazon Resource Name (ARN) -> go to the previous tab in bucket policy, copy Bucket ARN, and paste it in.
   - Click on add statement then Generate Policy.

5. **Copy the generated code and paste it in the policy.**

6. **When you paste in the policy, make sure resources should look like this:**
   - `"Resource": "arn:aws:s3:::your-bucket-name/*"`

*Now, your object URL is public.*



# S3 Versioning

S3 versioning is a powerful feature provided by Amazon Simple Storage Service (S3) that allows you to keep multiple versions of an object in the same bucket. This feature is particularly valuable for maintaining a version history of your objects and recovering from accidental deletions or overwrites.

## Enable Versioning on an S3 Bucket

To enable versioning on an S3 bucket, follow these steps:

1. **Using the AWS Management Console:**
   - Open the S3 console.
   - Select the target bucket.
   - Navigate to the "Properties" tab.
   - Click on "Versioning" and then click "Enable versioning."

    ```markdown
    ![Enable Versioning](path/to/enable-versioning-screenshot.png)
    ```

   This ensures that every time you upload a new version of an object, S3 automatically archives the previous version, providing you with a robust version history.

By enabling versioning, you add an extra layer of protection to your data, making it easier to track changes and recover from unintentional modifications.

