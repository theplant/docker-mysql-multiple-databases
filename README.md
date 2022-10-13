# Using multiple databases with the official MySQL Docker image

## Usage

Pass the `MYSQL_MULTIPLE_DATABASES` environment variable
to the container:

    myapp-mysql:
        image: public.ecr.aws/theplant/mysqlmd:5
        environment:
            - MYSQL_MULTIPLE_DATABASES=db1,db2
            - MYSQL_ROOT_PASSWORD=123

## Push image

Please assume AWS IAM `developer` role before push image
```
[alias.main-developer]
arn = "arn:aws:iam::562055475000:role/developer"
```

```
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/theplant
```