# Aim of this project
Make use of my newly gained IaC and cloud knowledge by automating the creation of an AWS infrastructure to host my Angular portfolio (currently hosted on github pages).  
This will not only allow me to gain hands on experience with Terraform, but AWS as well, as access policies and other configuration of AWS resources will need to be written and tested.  
The main repo for this project will remain private until completion, as I am experimenting with access policies, roles, credentials and other sensitive information. Once completed, any sensitive information that remains wil be removed and the rest of the project will be re-uploaded here.  
  
However, this README will be updated regularly, as new steps are completed, in order to publically log my progress and document my challenges.

# Planification
## Infrastructure
- Set up AWS credentials for Terraform (IAM user & role with appropriate policies)  
- Configure Terraform to use those credentials  
- Use Terraform to deploy a single s3 bucket on AWS with the appropriate policy  

## Deployment 
- Use Terraform to clone the portfolio from github into s3 bucket
- Use Terraform to build and deploy the website within the s3 bucket  

## Redirection
- Acquire a domain/subdomain name
- Use Terraform and Amazon Route 53 to redirect the s3 bucket link to the custom domain  

# Development log
## Granting Terraform access to AWS Resources
- Determined that creating a user specifically for Terraform and using its access keys involves long-term credentials, that I will need to rotate manually or through a script, which I'm not a fan of.  
- Use of a role is preferred, to which a restrictive policy is attached (limited access to s3 buckets only - least privilege applied)  
- Make use of AWS CLI `assume-role` command, as it will generate **_temporary_** credentials  
- Create bash script to run `assume-role` and attribute to Terraform (should be run in CI/CD pipeline)
- Detach role (in bash script) once Terraform has performed its duties
- This will ensure no permanent credentials or permissions are given to external services
