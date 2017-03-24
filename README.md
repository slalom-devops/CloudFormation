# CloudFormation

This repo is for people to pull down an example template on building AWS infrastructure.  Review the diagram on the confluence page: https://slalom.atlassian.net/wiki/display/DEVOPS/Pivoting+to+DevOps+and+Cloud for a visual guide on what you should be attempting to create, below is a list of resources you will need to create.  

### Infrastructure Template Should Include: <br />
    1. VPC
    2. Two Private and two Public Subnets (each subnet in a different availability zone)
    3. Private and Public Route Tables
    4. Internet Gateway for Public Subnets, attach to Public Route Table
    5. Elastic IP for NAT Gateway
    6. NAT Gateway for Private Subnets, attach to Private Route Table
    7. Two Security Groups:
        A. One for traffic from the internet to elastic load balancers
        B. Allow traffic from the load balancer (public subnet) to the applications (private subnets).
    
    Tag all your resources (this will tag your resource with what your Stack name is and append -VPC):       
    Resources:
      VPC:
        Type: 'AWS::EC2::VPC'
        Properties:
          CidrBlock: 10.10.0.0/16
          EnableDnsSupport: true
          EnableDnsHostnames: true
          Tags:
          - Key: Name
            #This will substitute the stack name you supplied while running the template
            Value: !Sub '${AWS::StackName}-VPC'
    
    Export all your resources: 
    Outputs:
      VPC:
        Description: 'VPC'
        Value: !Ref VPC
        Export:
            Name: !Sub '${AWS::StackName}-VPC'
            
### Build Stack:
    1. Navigate to CloudFormation in AWS Console 
    2. Browse and upload your template file
    3. Name your stack, with your name, such as: Michael-Towbin-TestStack.
       This helps with figuring out who owns what resources and makes the exports unique.
    4. Will probably need to make some edits (if you built yours with json, probalby a lot of edits)
    5. Rinse and repeat steps 2-4 until it runs.
    
### Resources    
Use the following page as a reference tool: <br />
http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html
