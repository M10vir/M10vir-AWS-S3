# M10vir-AWS-S3
Step-by-Step Guide to Creating, Managing, and Hosting Websites with AWS S3

# README.md

## AWS S3 Project: Creating, Managing, and Hosting Websites

### Introduction

This project demonstrates how to create an Amazon S3 bucket, upload and access files, grant public access, host a static website, enable versioning, and delete the S3 bucket. This guide will walk you through each step, providing clear instructions and necessary code snippets.

### Steps

#### 1. Creating an Amazon S3 Bucket

1. **Sign in to AWS Management Console**:
   - Navigate to the AWS Management Console.
   - Use your AWS account credentials to log in.

2. **Access Amazon S3**:
   - In the search bar at the top, type “S3” and select “S3” from the dropdown.

3. **Create a New Bucket**:
   - Click on the “Create bucket” button.
   - Enter a unique bucket name (bucket names must be globally unique).
   - Choose the AWS Region where you want the bucket to be created.
   - Configure options as needed and click “Create bucket”.

#### 2. Uploading and Accessing Files

1. **Uploading Files to S3 Bucket**:
   - Open your S3 bucket by clicking on the bucket name.
   - Click on the “Upload” button.
   - Drag and drop files or click “Add files” to select files from your local machine.
   - Click “Upload” to start the upload process.

2. **Accessing Files**:
   - Once the files are uploaded, click on the file name to view its properties.
   - The “Object URL” can be used to access the file directly if public access is granted.

#### 3. Granting Public Access Manually

1. **Adjust Bucket Permissions**:
   - Go to the “Permissions” tab of your S3 bucket.
   - Click on “Block public access (bucket settings)”.
   - Uncheck “Block all public access” and acknowledge the warning by clicking the check box.
   - Click “Save changes”.

2. **Set Object Permissions**:
   - Go to the “Objects” tab, select the files you want to make public.
   - Click on “Actions” and select “Make public”.
   - Confirm the changes.

#### 4. Granting Public Access via Bucket Policy

1. **Define Bucket Policy**:
   - Go to the “Permissions” tab and scroll down to the “Bucket policy” section.
   - Click “Edit” to open the policy editor.

2. **Add Policy JSON**:
   - Paste the following JSON, replacing `YOUR-BUCKET-NAME` with your bucket name:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
         }
       ]
     }
     ```
   - Click “Save changes” to apply the policy.

#### 5. Hosting a Static Website

1. **Enable Static Website Hosting**:
   - Go to the “Properties” tab of your S3 bucket.
   - Scroll down to “Static website hosting” and click “Edit”.
   - Select “Enable” and specify the “Index document” (e.g., `index.html`).
   - (Optional) Specify the “Error document” (e.g., `error.html`).
   - Click “Save changes”.

2. **Accessing the Hosted Website**:
   - The “Bucket website endpoint” will be displayed in the “Static website hosting” section.
   - Use this endpoint URL to access your static website.

#### 6. Enabling Versioning in AWS S3

1. **Enable Versioning**:
   - Go to the “Properties” tab of your S3 bucket.
   - Scroll down to “Bucket Versioning” and click “Edit”.
   - Select “Enable” and click “Save changes”.

2. **Managing Versions**:
   - Upload new versions of files to keep track of changes.
   - Access previous versions of files through the S3 console by selecting the file and clicking on “Versions”.

#### 7. Deleting S3 Bucket

1. **Delete Objects in the Bucket**:
   - Open your S3 bucket and go to the “Objects” tab.
   - Select all objects and click “Actions” > “Delete”.
   - Confirm the deletion.

2. **Delete the Bucket**:
   - Go back to the S3 bucket list.
   - Select the bucket you want to delete.
   - Click “Delete” and confirm the deletion by typing the bucket name.

### Conclusion

By following these steps, you can efficiently manage your S3 buckets, upload and access files, configure public access, host a static website, enable versioning, and delete the bucket when no longer needed. Amazon S3 provides a flexible and robust storage solution, making it a great choice for various applications.
