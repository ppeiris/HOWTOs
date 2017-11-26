# AWS Command Line 
## Configure

### - Set up initial configuration
```
aws configure
AWS Access Key ID [****************WYFA]: XXXXXXXXXXXXXXXXXXXXXXXXX
AWS Secret Access Key [****************W5F2]: XXXXXXXXXXXXXXXXXXXXXXXXXXXXX
Default region name [us-east-1]:
Default output format [None]:
```
- aws credential are stored in ~/.aws/
- Output formats are: JSON (default), text, table

### Change the default output format
```
ppeiris@dev$ aws ec2 describe-instances --output table | text | json
```

Getting Help 
```
$ aws --version
$ aws aim help
```

