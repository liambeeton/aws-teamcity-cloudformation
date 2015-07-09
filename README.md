# AWS TeamCity CloudFormation

CloudFormation template for automated setup of an EC2 instance with TeamCity installed.

## create.sh

```sh
$ aws cloudformation create-stack --stack-name teamcity --template-body file://teamcity-server.template --region eu-west-1
```

## delete.sh

```sh
$ aws cloudformation delete-stack --stack-name teamcity --region eu-west-1
```

## Image and Instance Type

```sh
"ImageId":"ami-c1740ab6",
"InstanceType":"t2.medium"
```

## Volume Size Config

```sh
"BlockDeviceMappings":[
	{
  		"DeviceName":"/dev/sda1",
  		"Ebs":{
     		"VolumeSize":"50"
  		}
	},
	{
  		"DeviceName":"/dev/sdm",
  		"Ebs":{
     		"VolumeSize":"50"
  		}
	}
]
```

## TeamCity Download Path

```sh
"C:\\TeamCity-9.0.5":"http://download.jetbrains.com/teamcity/TeamCity-9.0.5.tar.gz"
```