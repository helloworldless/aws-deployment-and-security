# Securing Infrastructure in AWS

# Deploy

1. Run the command below

`aws cloudformation deploy --template-file ./hbfl.start.template --stack-name hbfl-stack --parameter-overrides ImageIdParameter=ami-0323c3dd2da7fb37d --capabilities CAPABILITY_IAM`

## Notes

-   In the template, for the resources of `"Type": "AWS::EC2::Subnet",`, we have
    `"MapPublicIpOnLaunch": true`. This would normally be false as a security
    precaution. But here we're connecting to GitHub to download the source.
    That's the only reason we need a public IP.
-   Use VPC Flow Logs to inspect VPC connection IPs, decisions, etc.
-   CloudTrail provides comprehensive audit of all activities on your account
