# AWS Command Line
- AWS CLI is a case sensitive framework 

## Configure

### - Set up initial configuration
```
$ aws configure
$ AWS Access Key ID [****************WYFA]: XXXXXXXXXXXXXXXXXXXXXXXXX
$ AWS Secret Access Key [****************W5F2]: XXXXXXXXXXXXXXXXXXXXXXXXXXXXX
$ Default region name [us-east-1]:
$ Default output format [None]:
```
- aws credential are stored in ~/.aws/
- Output formats are: JSON (default), text, table

### - Change the default output format
```
$aws ec2 describe-instances --output table | text | json
```

### - Getting Help 
```
$ aws --version
$ aws aim help
```

### - Set up Autocomplete
http://docs.aws.amazon.com/cli/latest/userguide/cli-command-completion.html

- get the shell and aws_completer location
```
$ echo $SHELL
/bin/bash
$ which aws_completer
/staff/ppeiris/anaconda2/envs/tensorflow/bin/aws_completer
```
- set up with the complete command
```
$ complete -C '/staff/ppeiris/anaconda2/envs/tensorflow/bin/aws_completer' aws
```
Now you can double tap TAB key to autocomplete aws commands 


### - Filters Option

You can use filters to limit the output of a command. This filtering happen on the server side.

```
$ aws ec2 describe-instances --filter Name=instance-type,Values=t2.micro
```
### - Query Option

You can also use the query option to limi the results. This happen on the client side (i.e: this is very similar to grep option)

```
$ aws ec2 describe-regions --query 'Regions[?RegionName==`us-west-1`]'
```
Output 
```json
[
    {
        "RegionName": "us-west-1",
        "Endpoint": "ec2.us-west-1.amazonaws.com"
    }
]
```





