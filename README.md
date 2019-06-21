# Using multiple databases with the official MySQL Docker image

## Usage

### By building a custom image

Clone the repository, build and push the image to your Docker repository,
for example for Google Private Repository do the following:

    docker build --tag=theplant/mysqlmd:5 .
    gcloud docker -- push theplant/mysqlmd:5

You still need to pass the `MYSQL_MULTIPLE_DATABASES` environment variable
to the container:

    myapp-mysql:
        image: theplant/mysqlmd:5
        environment:
            - MYSQL_MULTIPLE_DATABASES=db1,db2
            - MYSQL_ROOT_PASSWORD=123

