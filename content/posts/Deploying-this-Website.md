---
title: 'Deploying this webpage'
date: 2024-03-04T00:07:46Z
type: "post"
tags: ["Devops", "Cloud", "Automation"]
showTableOfContents: true
---

## Introduction

I figured the most appropriate way to kick off this blog is give an overview as to why it was created and how. As for the former, I wanted a blog to catalogue and provide an in-depth write-up for the various projects and certifications I will pursue. Initially, options such as WordPress or Squarespace were considered, as a fast an easy way to get it up and running. After ruminating on these options, I decided to take the simple process of creating a blog in a different direction.

One which facilitated hands-on experience with multiple technologies and subject domains. This involved handling all parts of the creation of the blog, ranging from setting up and configuring the VPS the blog is hosted on, purchasing a domain name, and handling the networking and web server to get the site up and running.

The Infrastructure as Code (IAC) related aspects to the project can be found [here](https://github.com/WanderingShibe/Static-page-IAC)

The blog webpage code and the CI/CD pipeline used for deployment can be found [here](https://github.com/WanderingShibe/Static-page-code)

## Methodology

Becoming a Devops engineer is the current direction I’m aiming my career towards. The aim for completing this blog page was to improve my hands-on experience and knowledge in the following subject domains

- Networking
- IAC
- Cloud
- Automation

Planning how I wanted to cover all these subject areas was something that took lots of consideration. After deciding on the tools and technologies I wanted to use to create this blog, I outlined the following steps I need to take to complete this task

- Automate the creation of a VPC in Oracle Cloud by using Terraform
- Configure the appropriate ingress/egress rules using Terraform
- Create an Ansible playbook to handle the necessary configuration for the VPC
- Purchase a domain name and link the domain to the webserver
- Create a static website and push the website to my webserver securely using GitHub Actions
- Create a CI/CD pipeline that can be used to tests and rebuilds the website when new content is added  

## Factors to Consider
Something I learned from my previous role is that if something has to be done more than once, find a way to automate it. While this project one only takes one server into consideration, and in many ways, it may be faster to configure everything manually, it's not the proper way of doing things. I wanted my approach to be scalable and repeatable. I want to be able to teardown the entire thing and be able to get the exact same build with ease.  Considering automation throughout the entire process made me conscious of how I planned the project.

Additionally, security was another factor I considered. Something my masters in cyber security taught me is how to take security into consideration when creating projects. As an example, it's much better practise to login to my server using generated SSH keys versus using a username and password. It's much better to store sensitive data as variable and gitignore then during commits than it is to hardcode values. 

## Results
Overall, I'm happy with how this project turned out! I managed to learn new technologies, and further hone my abelites with the existing ones I'm familiar with. It's nice to have something that I can use and show off to people than another project that is forgotten in a git repository.

## Areas to Improve/Consider
If I were to expand on this project or redo it I'd do the following
- Use a different cloud provider such as AWS. This will allow me get practise and access other services such as S3, CloudFront and Lambda
- Look to implementing health checks and load balancing to scale with incoming demand
- Look at how I can deploy the site on Kubernetes or EKS