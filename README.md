# CloudFormation

This repo is for people to pull down an example template on building AWS infrastructure.  

### Infrastructure Template Should Include: <br />
    1. VPC
    2. Private and Public Subnets
    3. Route Table for Each Subnet
    4. Internet Gateway for Public Subnet
    5. Attach to Public Subnet
    6. Elastic IP for NAT Gateway
    7. NAT Gateway for Private Subnet
    8. Attach to Private Subnet

### Build Stack
    1. Navigate to CloudFormation in AWS Console 
    2. Browse and upload your template file
    3. Name your stack, with your name, such as: Michael-Towbin-TestStack
    4. Will probably need to make some edits (if you built yours with json, probalby a lot of edits)
    5. Rinse and repeat steps 2-4 until it runs.
    
### Resources    
Use the following page as a reference tool: <br />
http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
