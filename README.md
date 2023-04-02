# cw-todo-app
This project aims to create a Jenkins pipeline to deploy web-page written Nodejs and React Frameworks on AWS Cloud Infrastructure using Ansible. Building infrastructure process is managing with control node utilizing Ansible. This infrastructure has 1 Jenkins Server (`Amazon Linux 2 AMI`) as Ansible Control Node and 3 EC2's as worker node (`Red Hat Enterprise Linux 8 with High Availability`). These EC2's will be launched on AWS console. Web-page has 3 main components which are Postgresql, Nodejs, and React. Each component is serving in Docker container on EC2s dedicated for them. Postgresql is serving as Database of web-page. Nodejs controls backend part of web-side and react controls frontend side of web-page. The Web Application will be deployed using Nodejs and React framework and should be accessible via web browser from anywhere on port 3000.

In my case; first of all I launched Jenkins Server with security group allowing SSH (port 22) and HTTP (ports 80, 8080) connections. After that, I have followed the steps indicate below👇

📌Create infrastructure with Terraform,
📌Create an image repository on ECR for the app,
📌 Build the application Docker image and push it to the same ECR repository with different tags,
📌 Deploy the application on AWS EC2's with Ansible,
📌 Make a failure stage and ensure to destroy infrastructure, ECR repo and docker images when the pipeline failed.

I used Jenkins Pipeline for building, testing, deploying and facilitating continuous integration and continuous delivery. It worked very well with this project.
