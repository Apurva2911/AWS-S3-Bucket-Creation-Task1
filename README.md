# ☁️ AWS S3 Bucket Project

This project demonstrates how to create and configure an Amazon S3 bucket using the AWS Management Console and upload files for public access.  
It also includes steps to verify the uploaded object via a browser link.

---

## 🚀 Project Overview

Amazon S3 (Simple Storage Service) is used to store and retrieve data at any time.  
In this project, we create a bucket, upload a file (object), make it public, and verify access through the object URL.

---

## 🧭 Steps Performed

### 1️⃣ Create an S3 Bucket
1. Go to the S3 service in the AWS Management Console.  
2. Click Create bucket.  
3. Enter a unique bucket name and select a region.  
4. (Optional) Uncheck Block all public access if you want to host static files.  
5. Click Create bucket.

---

### 2️⃣ Upload an Object
1. Open the created bucket.  
2. Click Upload → Add files.  
3. Select your file (e.g.index.html, image.png, etc.).  
4. Click Upload.

---

### 3️⃣ Make Object Public
1. Select the uploaded file.  
2. Click Actions → Make public using ACL(if ACLs are enabled).  
   OR  
3. Go to Permissions → Bucket Policy and add a public read policy:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::your-bucket-name/*"
       }
     ]
   }

