# ami-lookup
CloudFormation region maps make CloudFormation templates more portable, but how do you look up the regions for multiple images.  Manually? Oh the horror.

This utility addresses the issue.  Based on an Amazon Machine Image, it creates a cross-region mapping for the same image.  

Python and Pip in the usage instructions below assume the Python3 versions.

## Usage

Assuming the AWS cli is installed and configured:

```
pip install boto3
pop install docopt
python ami_lookup.py AMI-TO-MAP REGION-FOR-AMI-TO-MAP
```

## Example Usage / Output

```
python ami_lookup ami-03291866 us-east-2
|--------------------------------------------------|
| Generating map.  This will take several seconds. |
| Please wait...                                   |
|--------------------------------------------------|
"RegionMap" : {
	"us-east-2"   : { "AMI" : "ami-03291866"},
	"us-east-1"   : { "AMI" : "ami-6871a115"},
	"us-west-1"   : { "AMI" : "ami-18726478"},
	"us-west-2"   : { "AMI" : "ami-28e07e50"},
	"ap-south-1"   : { "AMI" : "ami-5b673c34"},
	"ap-northeast-2"   : { "AMI" : "ami-3eee4150"},
	"ap-southeast-1"   : { "AMI" : "ami-76144b0a"},
	"ap-southeast-2"   : { "AMI" : "ami-67589505"},
	"ap-northeast-1"   : { "AMI" : "ami-6b0d5f0d"},
	"ca-central-1"   : { "AMI" : "ami-49f0762d"},
	"eu-central-1"   : { "AMI" : "ami-c86c3f23"},
	"eu-west-1"   : { "AMI" : "ami-7c491f05"},
	"eu-west-2"   : { "AMI" : "ami-7c1bfd1b"},
	"eu-west-3"   : { "AMI" : "ami-5026902d"},
	"sa-east-1"   : { "AMI" : "ami-b0b7e3dc"},
}

```