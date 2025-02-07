# Created data visualizations using Amazon S3 and Amazon Quicksight, working with a large dataset of best-selling Amazon products
In this project, you will learn how to create visualizations from a large dataset using Amazon S3 and Amazon QuickSight. 

We will work with a dataset containing 50,000 best-selling products on Amazon.com, including categories, prices, customer reviews, and sales rankings. By leveraging Amazon S3 for data storage and Amazon QuickSight for analysis, you can process and present data more efficiently. This project covers the steps of uploading the dataset to S3, connecting it to QuickSight, and creating various visualizations to analyze trends and sales patterns. Let's get started and uncover valuable insights from this large dataset! 

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
Region: Select the nearest region (e.g., Asia Pacific (Singapore)).
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
