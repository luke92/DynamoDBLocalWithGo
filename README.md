# DynamoDBLocalWithGo
DynamoDB Local with Go using NoSQL Workbench

# How to run in Windows

# Requisites
- NoSQL Workbench (https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/workbench.html)
- AWS CLI (https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) 
- DynamoDBLocal (https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html)
- Here in the repo is the DynamoDBLocal with region `sa-east-1`

## 0. Run NoSQL Workbench
- In Operation Builder add new DynamoDBLocal Connection
- Copy Credentials (Access Key ID and Secret access key)

## 1. Configure AWS
- Run `aws configure`
- Put AWS Access Key Id AND Secret access key from NoSQL workbench 
- Put region of DynamoDBLocal (for example `sa-east-1`)

## 2. Run DynamoDBLocal

If you're using Windows PowerShell, be sure to enclose the parameter name or the entire name and value like this:

- Run in a Powershell (or run `ryndynamo.ps1`)
- `java -D"java.library.path=./DynamoDBLocal_lib" -jar DynamoDBLocal.jar -sharedDb`

## 3. Run Code from go-dynamodb-reference
- Change in the file `dynamodb.go`
- Region (`config.WithRegion`)
- AccessKeyId
- SecretAccessKey
- SessionToken (this should be empty)
- `go get .`
- `go run .`