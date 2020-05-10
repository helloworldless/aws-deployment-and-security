# Deploying Applications to AWS

## Deploy Cloud Formation Template

1. Run the command below
2. ImageIdParameter - Get the latest Amazon Linux AMI ID from EC2 Console
3. VPCIdParameter - Use the default AWS VPC
4. SubnetListParameter - Get the IDs of least two subnets from the VPC console under Subnets, e.g. `us-east-1a`, `us-east-1b`

`aws cloudformation deploy --template-file ./hbfl.start.template --stack-name hbfl-stack --parameter-overrides ImageIdParameter=ami-0323c3dd2da7fb37d VPCIdParameter=vpc-0a358a64ae71dc0eb SubnetListParameter=subnet-0fd30ed5b383a78fb,subnet-043f91637234fc4bf --capabilities CAPABILITY_IAM`