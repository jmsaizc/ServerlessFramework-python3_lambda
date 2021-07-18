# ServerlessFramework-python3_lambda
Create a python3 numpy lambda using Serverless Framework (https://www.serverless.com/)

## Prerequisites
- AWS CLI
- Docker Installed and Running in system
- Node

## Install Serverless Framework 
````
npm install -g serverless
````
## Create Python3 service
````
serverless create \
 --template aws-python3 \
 --name ServerlessFramework-python3_lambda \
 --path ServerlessFramework-python3_lambda 
````
Will create ServerlessFramework-python3_lambda folder and handler.py serverless.yml files

## Create Python3 and activate Virtual Env
````
virtualenv venv --python=python3
source venv/bin/activate
````
## Copy from this repo or code your handler.py
````
# handler.py
import numpy as np
def main(event, context):
  a = np.arange(15).reshape(3, 5)
  print("Your numpy array:")
  print(a)
if __name__ == "__main__":
  main('', '')
````
Example from Numpy Quick Start - https://numpy.org/doc/stable/user/quickstart.html

## Install Numpy
````
pip install numpy
or
pip3 install numpy
````
Virtualenv was initialized with --python=python3, can use pip instead pip3 ;-)

## Create requirements.txt file
```` 
pip freeze > requirements.txt
````

## Test handler.py
````
python handler.py
Your numpy array:
[[ 0  1  2  3  4]
 [ 5  6  7  8  9]
 [10 11 12 13 14]]

````
## Copy serverless.yml

Copy serverless.yml from this repo

## Install 
Install serverless-python-requirements plugin:
````
npm init
node install serverless serverless-python-requirements --save
````
Default values are ok for npm init, this step will create new file "package.json" with node dependencies.

## Setup AWS
````
aws configure
````
Test running for example:
````
aws s3 ls 
````
To see buckets in your aws account

## Finally deploy lambda function using serverless framework
````
serverless deploy -v
````
## Delete function
````
serverless remove
````
## Deactivate virtualenv
````
deactivate
```