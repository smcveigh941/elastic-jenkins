# Elastic Jenkins
Configuration for quick deployment of an elastically scaled instance of a Jenkins server hosted on AWS

## Prerequisites
You need to have elastic beanstalk cli installed on your machine to be able to deploy this jenkins server to your own instance. For Mac, you can install it using Homebrew (https://brew.sh/)

```
brew install aws-elasticbeanstalk
```

For Linux and Windows, use the following instructions from Amazon.
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html

## Setup
1. From the root of this project, run the following command. This will create a `.elasticbeanstalk` directory containing the file `config.yml`.
```
eb init
```

2. In this `config.yml` file, add the entry:
```
deploy: 
  artifact: jenkins.zip
```

3. From the root directory of this project run the following command, this will begin the process of deploying your jenkins server. Follow the instructions on the CLI. Select YES when asked if you want to set up SSH with the instance. You should select Java 8 as the runtime environment.
```
eb create 
```

4. When the server is deployed, you will be able to visit the server at the url shown on your AWS elastic beanstalk page. When you visit the url, you will be asked to find the initial admin password at a given file location. You will need to SSH onto the instance to fetch this.
