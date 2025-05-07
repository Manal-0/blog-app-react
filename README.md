# Week-10 Assignment - MERN Stack Blog Application Deployment on AWS
-Student ID: SDA2020-Manal
-GitHub Repository: manal-0
-Date: May 2025

# Project Overview
For this project, I decided to deploy a MERN Stack (MongoDB, Express, React, Node.js) blog application on AWS. The goal was to build a fully functional application running efficiently on the cloud while following best practices for modern application deployment.

# The project included the following steps:

Frontend (React + Vite): Hosted on S3 for fast loading times and excellent response.

Backend (Express.js): Hosted on EC2 for scalability.

Database (MongoDB Atlas): Used to securely store blog data with scalability.

Media Storage: Managed through S3 to ensure fast and reliable access to images, videos, etc.

Process Management: Used PM2 to ensure backend processes run continuously without interruption.

# Technologies Used
AWS EC2: Hosting the backend.

AWS S3: Hosting the frontend and media files.

MongoDB Atlas: Cloud database storage.

PM2: Process management.

Vite + React: For frontend development.

Node.js + Express: For backend development.

# Deployment Steps
Clone the Project
I cloned the project repository to the EC2 Ubuntu instance to begin deployment.

MongoDB Setup

I created and configured a MongoDB Atlas cluster.

The EC2 IP was whitelisted, and I set up a user with credentials.

The .env file on the EC2 instance was updated with the correct MongoDB URI.

Backend Configuration and Launch

I installed the dependencies using npm install on the EC2 instance.

The .env file was configured with the API and media URLs.

I started the backend server using PM2 to ensure it runs continuously even after the session is closed.

Frontend Build and Deployment

I navigated to the frontend directory and ran npm run build to generate production-ready files.

Using AWS CLI, I synced the dist/ folder to the S3 bucket.

I updated the S3 bucket policy to allow public access to the files.

Media Bucket Configuration

I created a separate S3 bucket named manal-blogapp-media for media file storage.

The frontend .env file was updated to use the media bucket URL.

Testing

I tested the backend by sending requests to the EC2 public IP on port 5000.

I confirmed that the frontend loaded correctly from the S3 website endpoint.

I verified that the media upload functionality and API interactions were working.

# What I Learned
Throughout this project, I learned how to integrate various technologies like React, Express.js, and AWS services with MongoDB Atlas into a cohesive application.

# Files and Deliverables
screenshots/
A folder containing screenshots for each deployment step:

_ec2_port_5000_rule.png
Screenshot showing the EC2 instance’s security group rule allowing traffic on port 5000, necessary for backend communication.

media_bucket_public_url.png
Screenshot showing the public URL of the S3 media bucket, where media files are stored and accessed by the frontend.

api_welcome_message.png
Screenshot displaying the "Welcome" message from the API, confirming the backend is running correctly.

backend_curl_localhost.png
Screenshot showing the result of a curl command to the localhost on the EC2 instance, verifying that the backend is responding properly.

frontend_build_folder_exists.png
Screenshot showing that the build folder exists after running the frontend build process (npm run build), ensuring production files are created.

frontend_build_pnpm.png
Screenshot showing the successful frontend build using pnpm , indicating that the build process completed without errors.

frontend_env_vite_base_and_media_url.png
Screenshot of the .env file for the frontend, highlighting the configuration of the base URL and media storage URL.

media_bucket_public_url.png
Another screenshot showing the media bucket’s public URL , confirming accessibility for media assets.

pm2_backend_app_status.png
Screenshot of the PM2 process manager, showing the status of the backend application to ensure it's running as a persistent process.

port_5000.png
Screenshot showing the backend API accessible on port 5000, confirming that the server is exposed and reachable.

s3_buckets_info.png
Screenshot of the S3 bucket configurations, showing both the frontend and media buckets used for the project.

s3_sync_frontend_upload.png
Screenshot showing the successful synchronization of the frontend build folder to the S3 bucket using the AWS CLI.

README.md
This file documenting the entire deployment workflow.
# Conclusion
This project gave me a solid understanding of deploying a full-stack application on AWS, from setting up the backend to hosting static files.
