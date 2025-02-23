# Aim of this project
Make use of my newly gained IaC and cloud knowledge by automating the creation of an AWS infrastructure to host my Angular portfolio (currently hosted on github pages).  
This will not only allow me to gain hands on experience with Terraform, but AWS as well, as access policies and other configuration of AWS resources will need to be written and tested.  
The main repo for this project will remain private until completion, as I am experimenting with access policies, roles, credentials and other sensitive information. Once completed, any sensitive information that remains wil be removed and the rest of the project will be re-uploaded here.  
  
However, this README will be updated regularly, as new steps are completed, in order to publically log my progress and document my challenges.

# Planification
## Infrastructure
- Set up AWS credentials for Terraform (IAM user & role with appropriate policies)  
- Configure Terraform to use those credentials  
- Use Terraform to deploy a single private s3 bucket on AWS with the appropriate policy  

## Deployment 
- Use Terraform to clone the portfolio from github into s3 bucket
- Use Terraform to build and deploy the website within the s3 bucket

## Redirection
- Acquire a domain/subdomain name (explore CloudFront avenue; more research and understanding needed)
- Use Terraform and Amazon Route 53 to redirect the s3 bucket link to the custom domain
