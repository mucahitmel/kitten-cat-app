AWSTemplateFormatVersion: 2010-09-09

Description: 
 
  Bu bizim ilk ekip calismamis.

Resources:
  MyInstance:
      Type: AWS::EC2::Instance
      Properties:         
        ImageId: ami-0715c1897453cabd1
        InstanceType: t2.micro
        KeyName: muco
        SecurityGroups: 
          - !Ref SecGroup
        Tags:
          - Key: Name 
            Value: MyInstance
        UserData: 
          Fn::Base64: |
            #!/bin/bash
            sudo dnf update -y
            sudo dnf install -y httpd
            sudo dnf install git -y
            systemctl start httpd
            systemctl enable httpd
            cd /var/www/html
            rm -rf index.html
            wget https://raw.githubusercontent.com/mucahitmel/yeni/main/index.html
            wget https://raw.githubusercontent.com/mucahitmel/yeni/main/cat0.jpg
            wget https://raw.githubusercontent.com/mucahitmel/yeni/main/cat1.jpg
            wget https://raw.githubusercontent.com/mucahitmel/yeni/main/cat2.jpg
              
  SecGroup:
      Type: AWS::EC2::SecurityGroup
      Properties:
        GroupDescription: Enable SSH.
        SecurityGroupIngress:
          - IpProtocol: tcp
            FromPort: 22
            ToPort: 22
            CidrIp: 0.0.0.0/0

          - IpProtocol: tcp
            FromPort: 80
            ToPort: 80
            CidrIp: 0.0.0.0/0
                  

         

  

