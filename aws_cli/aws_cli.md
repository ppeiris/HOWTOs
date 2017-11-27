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

### - Dry Run

Dry run allow to run the command line options without really making any real effect. This wont give us any output, it will give a message saying the command would have success or fail. 

```
$ aws ec2 describe-regions --dry-run
```
Output 
```
An error occurred (DryRunOperation) when calling the DescribeRegions operation: Request would have succeeded, but DryRun flag is set.
```

## Process JSON data using Jamespath query language

JAMESpath is a query language for JSON data (http://jmespath.org/). 

Install using conda

```
conda install -c conda-forge jmespath
```

Install JAMESpath terminal 

https://github.com/jmespath/jmespath.terminal
```
pip install jmespath-terminal
```

### - How to use jpterm 
Following command get the list of reagions in JSON format and open up the jamespath terminal to interact with the data. 
```
aws ec2 describe-reagions | jpterm
```
[iamge](https://cloud.githubusercontent.com/assets/368057/5158770/6a6afb6e-72fe-11e4-8be3-893edf21920e.gif)

.. image:: https://cloud.githubusercontent.com/assets/368057/5158770/6a6afb6e-72fe-11e4-8be3-893edf21920e.gif


