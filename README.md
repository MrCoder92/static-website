# Static-website
AWS Static Website using S3 and Route 53
In this project, I hosted a Static Website using Amazon S3 and Route 53 while keeping in mind Securities Best Practices, to achive the goal.

# Create a customize domain using the Amazon Route 53
Head to the Amazon Route 53 to create/purchase your domain. It can take 10 minutes or maximum 3 days to successfuly activate the domain. 

When successfully activated you will receive a confirmation email. Ones confirmed, head to the Amazon S3 to create your bucket.


# Use an Amazon S3 bucket to host a sample website
Create a new S3 bucket. This bucket will be used to host the website.
Make sure your bucket name is the same as your domain name. 

Select a region close to your location to reduce latency
Uncheck the Block All Public Access to make the website publicly accessible to users.
Acknowledge the warning and keep the rest as default and select create bucket. 

Click into your bucket name (domain) and select upload to upload your website (in code).
Upload your website files to the S3 bucket using the `"Upload"` button in the `"Overview"` tab or using the AWS CLI.

# Enable a static website hosting and direct the domain to the S3 bucket
Navigate to the Route 53 service and create a new hosted zone for your domain name.
Make sure the website is enabled for static website hosting and has the right permissions for users to access it. 

Select properties and scroll all the way to the bottum to Static website hosting.
By default it is disabled, select edit and type the default page for the website; in this case (index.html) and save changes.

Now click on permissions to add/attach bucket policies.
click edit and attach your bucket policies and click save changes. 

We have now configured the bucket to have a sample website publicly accessible to viewers.
Open the sample website to access the webpage. 

# Changing the Amazon provided URL to your custom URL
To change the Amazon provided URL to your custom URL, Head to Amazon Route 53, click on hosted zone.
click into the domain name and add additional record to connect the bucket to Route 53.

Select the simple routing policy, for the value the endpoint should be alias to S3 website endpoint, select the region the website is hosted and finally select the S3 endpoint which is already provided.

If you have configured SSL for your domain, you can obtain an SSL certificate using the AWS Certificate Manager.

Once your DNS settings have propagated, you can view your website at the URL http://<YOUR-DOMAIN-NAME> or https://<YOUR-DOMAIN-NAME> if you have configured SSL.

# Clean Up
To clean up the resources when you're done, delete the S3 bucket and the Route 53 hosted zone.

# Files
This repository contains the following files:

  `BucketPolicy`: The file which contains the the set of permissions.

  `index.html`: Contains the code for the default page for the website.

  `README.md`: This file.

# Contributing
If you find any issues or would like to contribute to this project, please open an issue or a pull request on GitHub.
