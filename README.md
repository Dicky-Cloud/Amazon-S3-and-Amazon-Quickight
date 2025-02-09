# Created data visualizations using Amazon S3 and Amazon Quicksight, working with a large dataset of best-selling Amazon products

![s3 and quicksight drawio](https://github.com/user-attachments/assets/3d222e04-4726-4ee5-be7a-8839d84e6c8d)

In this project, you will learn how to create visualizations from a large dataset using Amazon S3 and Amazon QuickSight. 

We will work with a dataset containing 50,000 best-selling products on Amazon.com, including categories, prices, customer reviews, and sales rankings. By leveraging Amazon S3 for data storage and Amazon QuickSight for analysis, you can process and present data more efficiently. This project covers the steps of uploading the dataset to S3, connecting it to QuickSight, and creating various visualizations to analyze trends and sales patterns. Let's get started and uncover valuable insights from this large dataset! 
This Tutorial from https://github.com/techwithlucy

# What you will accomplish
in this tutorial, you will: 

• Download the dataset and prepare the necessary files.

• Store the dataset in Amazon S3 for scalable storage.

• Connect Amazon S3 to Amazon QuickSight for data analysis.

• Create visualizations to analyze trends and patterns.

# Prerequisites
• If you don't have an AWS account, you can watch tutorials on YouTube or follow the official guide on the AWS website to create one.

# Implementation
Use the following step-by-step written tutorial or watch this Tech With Lucy YouTube video to learn how Build: Visualize Data using Amazon QuickSight | AWS Project

# Step 1 : Download the Dataset
![image](https://github.com/user-attachments/assets/682c696c-3e0b-48ec-97b5-c7f9546d7ce3)
This image shows a GitHub repository named techwithlucy/youtube with a folder called 2-s3-quicksight. Inside this folder, there are two important files:

Amazon-Bestseller-Dataset.csv

This is a CSV file containing data on 50,000 best-selling products on Amazon.com.
manifest.json

This is a configuration file required to connect the dataset from Amazon S3 to Amazon QuickSight. It typically includes information like the S3 URL of your dataset.
Download Steps
To download these files:

Click on the file name (e.g., Amazon-Bestseller-Dataset.csv).
On the next page, click the "Raw" button.
Press Control+S (Windows) or Command+S (Mac) to save the file to your computer.
Repeat the process for the manifest.json file.
Once you've downloaded the files, you can proceed to the next step, which is uploading them to Amazon S3. 
Next Steps:
# Step 2 : Store the Dataset in Amazon S3
![image](https://github.com/user-attachments/assets/5a0488c1-ecb7-4c65-baa4-0331d30bac52)

Login to AWS
Go to the AWS Management Console and search for S3.

Create a Bucket
Click Create bucket on the S3 page.

Enter Bucket Details
Bucket Name: Enter a unique name (e.g., dicky-amazon-project).
Region: Select the nearest region (e.g., Us-east-1(Virginia)).
Configure Options
![image](https://github.com/user-attachments/assets/5abd4f7d-c81f-4bb5-888f-d507d56d7158)

Keep the default settings for Block Public Access (enabled).
Click Create bucket.

Explanation Before Uploading manifest.json
![image](https://github.com/user-attachments/assets/f465d93c-9228-4992-8820-0a53e09462ea)

Before uploading the manifest.json file to your system or application, you need to modify the code in a code editor like Visual Studio Code (VS Code) to ensure it reflects your S3 bucket name. Here's how you can do it:
Steps to Modify the Code in VS Code
Open the File in VS Code:

Open manifest.json in Visual Studio Code.
Locate the URIs Section:

Find this part of the code:
json
Copy
Edit
"URIs": [
    "s3://BUCKET-NAME/Amazon-Bestseller-Dataset.csv"
]
Replace BUCKET-NAME with Your S3 Bucket Name:

Change BUCKET-NAME to the actual name of your S3 bucket. For example:
json
Copy
Edit
"URIs": [
    "s3://dicky-amazon-project/Amazon-Bestseller-Dataset.csv"
]
Save the Changes:

After making the changes, press Ctrl + S (Windows) or Cmd + S (Mac) to save the file.
Verify the File:

Ensure that the bucket name and file path are correct and match the S3 configuration.


![image](https://github.com/user-attachments/assets/aa9b510f-7f83-4056-b965-c97c2457b7a1)

Look for the bucket name you created earlier, such as Dicky-Amazon-Project.
Click on the bucket name to open it.
Upload Files:

Click the Upload button within the bucket.
Upload the Amazon-Bestseller-Dataset.csv and manifest.json files you downloaded earlier.
Bucket Configuration (Optional):

Set access permissions and policies if needed.
Ensure that your files are accessible to other services like Amazon QuickSight.
This step is crucial to prepare your data for integration with Amazon QuickSight to create visualizations.

# Step 3: Connect S3 Bucket with Amazon Quicksight
![image](https://github.com/user-attachments/assets/cf32d312-26a4-49e0-9761-31b42c1a1c7b)
 Sign Up for Amazon QuickSight
Fill in Contact Information:
![image](https://github.com/user-attachments/assets/12f521eb-d0e9-4f54-bc0c-b180ccf0946b)

Enter the email address to receive notifications, for example: dickyanggraini2409@gmail.com.
Choose Authentication Method:

Select Use IAM federated identities & QuickSight-managed users to authenticate using IAM or QuickSight credentials.
If required, adjust other options like IAM Identity Center or Active Directory.
Select QuickSight Region:

Choose a region that matches your location. Example: US East (N. Virginia).
![image](https://github.com/user-attachments/assets/be82a327-d7be-4d2d-88ac-b26c5172eedc)

Setting Up QuickSight Access to AWS Services
Account Info:

QuickSight account name: Enter a name for your QuickSight account. Example: dicky.
This will be used to identify and sign in to your QuickSight account.
QuickSight Access to AWS Services:

IAM Role:

Use QuickSight-managed role (default): QuickSight will automatically create and manage an IAM role for accessing AWS resources.
Use an existing role: Select this option to use an existing IAM role.
Allow Access and Autodiscovery: Check the boxes for the services you want QuickSight to access:

Amazon Redshift: Connect to Redshift databases for analysis.
Amazon RDS: Access relational databases on RDS.
IAM: Enable integration with AWS Identity and Access Management.
Amazon S3: Provide access to S3 buckets.
Click Select S3 buckets to choose specific buckets for QuickSight access.
Continue:
![image](https://github.com/user-attachments/assets/a181ffbe-5994-4d89-b8b6-09b83a5a888a)

Click the Next or Continue button to proceed.
Link Amazon S3 Buckets
Select Buckets:

Check the bucket(s) to link with QuickSight, for example: dicky-amazon-project.
Use Select all to choose all available buckets.
Grant Write Permissions (Optional):

If using Athena Workgroup, check the box to grant Write permissions for Athena Workgroup.
Finish Setup:

Click the Finish button to save the configuration and complete the setup.
![image](https://github.com/user-attachments/assets/9c2ef9e0-cbcf-4896-81b3-e70fa76b5b3f)

# Step 4: Create Visualizations
![image](https://github.com/user-attachments/assets/eadd36d8-5c5f-4462-909b-e4c2daf1b879)
Select Data Source
On the Datasets page, click the New dataset button.
![image](https://github.com/user-attachments/assets/c3e1d225-5980-41a7-a2ab-19ec5143e94e)
Choose S3 as the data source.
Fill in Data Source Information
In the New S3 data source dialog, provide the following details:
Data source name: Enter a name for the data source, such as amazon-data-source.
Upload a manifest file: Enter the URL or upload a manifest file.
In the image, the manifest URL is:
https://dicky-amazon-project.s3.us-east-1.amazonaws.com/manifest.json.
Connect the Data
Click the Connect button to link the S3 data source to QuickSight.
Confirm and Proceed
Once successfully connected, QuickSight will prompt you to verify or process the data before creating the dataset.
Ensure that the displayed data matches your requirements, then proceed to the analysis phase.
![image](https://github.com/user-attachments/assets/aafbd4fc-12bc-4e4f-94b7-8ebac5393d51)
Create a Visualization
Select the connected dataset, such as amazon-data-source.
In the Data panel, choose the field you want to visualize, e.g., brand.
Configure the visualization:
Sort by: Select the brand field.
Aggregation: Choose Count to calculate the number of records by brand.
Sort order: Set to Descending to display brands with the highest record counts at the top.
Visualization Output
A bar chart will display the count of records for each brand.
For example, the chart shows the distribution of data for brands like "Amazon Renewed", "Motorcraft", and others.
Use the Apply button to save changes to the visualization.
