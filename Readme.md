## Notes for AWS command etc

## Create an EC2 instance
INSTANCE_ID=$(aws ec2 run-instances \
  --image-id ami-00e428798e77d38d9 --instance-type t2.micro --region us-east-2a \
  --query Instance[].InstanceId --output text )
  

## To watch for EC2 instance to be ready run the below wait command

aws ec2 wait intance-status-ok --instance-ids $INSTANCE_ID --region us-east-2a
