# awsresource-shell-script
aws resource collection shell script

#############################
https://www.youtube.com/watch?v=gx5E47R9fGk&t=122s
#############################
https://www.youtube.com/watch?v=cN4pt5KQ9eA
#############################


login through windows cmd prompt
Install aws cli on windows
go to cmd prompt

aws configure
access key: ## get it from aws security credentials ##
secret key: ## get it from aws security credentials create access key ##

ssh -i \Users\SONY\Downloads\shell.pem ec2-user@ec2-3-110-77-186.ap-south-1.compute.amazonaws.com

vi awsresource.sh

######
#Author:- Pramod Shivgunde
#
#Version:- V1
#
#This script will report the AWS resource usage
######

set -x  

#AWS S3
#AWS EC2
#AWS Lambda
#AWS IAM Users

#list s3 buckets
echo "Print list of s3 buckets"
aws s3 ls

#list EC2 Instances
echo "Print list of ec2 instances"
aws ec2 describe-instances | jq '.Reservations[].Instances[].Instanceid'

#list lambda
echo "Print list of lambda"
aws lambda list-functions

#list IAM users
echo "Print list of users"
aws iam describe-users

esc:wq!

chmod 777 awsresource.sh
./awsresource.sh
