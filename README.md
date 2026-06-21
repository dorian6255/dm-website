# Dorian MEURIN - Personnal Website 

This repository contains the source code and infrastructure-as-code for my personnal website.
you can see it here : 

## Project Goal

My goal for this project is to have a website that can be used as a sort of resume, easily accesible for everyone and in multiple languages. 
I want my website to be in a very simple format like Markdown, and use a tool to transform it into HTML/CSS.
I don't want to manage this website constantly, so I'll use a combo of terraform and Github action to deploy this website without human intervention and ideally require zero ongoing maintenance.

## How does it work ?

### Static Website Generation

I'm use [**Hugo**](https://gohugo.io/) to transform my Markdown into actual website in HTML/CSS. As I Devops, I am not interested in doing the HTML/CSS myself and I rather choose Hugo for it's features and speed, and to allow me to focus mainly on the content rather than the design.

### Infrastructure and Hosting

#### Website
* Hosted on [AWS S3](https://aws.amazon.com/fr/s3/) which is configured as a static website hosting service. This remove the need for managing, updating, securing ... a traditional web server
* Delivered through [AWS CloudFront](https://aws.amazon.com/fr/cloudfront/) for the low-latency delivery and for the HTTPS 
* Domain Name & DNS => [AWS Route 53](). While not the best or even cheapest option, it allows me to have a full AWS stack and it's easier to work with with Terraform.

### CI/CD and Automation (Gitops) 
* Infrastructure-as-code (**IAC**) : The entire AWS stack is provisionned using *Terraform*
* Github Action : On push on *Main* Branch, a github action is launched that will : Install Hugo, build the static assets and finally the output directly to the AWS S3 bucket (and invalidate the CloudFront Cache)

## Contact 

* **LinkedIn** : [linkedin.com/in/dorian-meurin](https://www.linkedin.com/in/dorian-meurin/)
* **Email** : //TODO 

