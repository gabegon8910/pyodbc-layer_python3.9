# Lambda Layer for ODBC with Python 3.9

This guide will walk you through the process of creating a Lambda Layer for using pyodbc with Python 3.9. This layer will allow you to connect to various data sources using the Open Database Connectivity (ODBC) protocol.

## Prerequisites
- A Linux machine with Docker installed.
- An SFTP application or access to a command-line interface (CLI) for uploading files to your server.

## Steps

1. Download the Docker image and create a new container by running the following command in your terminal:
```bash
docker run -it -v ${PWD}:/host-volume --entrypoint bash d3imos8910/odbc-lambda:python3.9
```

This command will launch a new container and mount the current directory as a volume named host-volume. It will also start a bash session within the container.

Once inside the container's bash session, copy the zip file containing the Lambda Layer to the host-volume directory:
``` bash
cp ~/pyodbc-layer_3-9.zip /host-volume/
```
Exit the container's bash session by running the following command:
``` bash
exit
```
If you have access to the file, upload the pyodbc-layer_3-9.zip file to your server using an SFTP application.

In the AWS Lambda Console, create a new layer or update an existing one, using the pyodbc-layer_3-9.zip as the source.

Attach the layer to the function where you want to use pyodbc

You should now be able to use pyodbc in your AWS Lambda function with Python 3.9. As always, make sure to test your function thoroughly before deploying it to a production environment.
Additional Resources

[Docker documentation](https://docs.docker.com/)
[AWS Lambda Layers documentation](https://docs.aws.amazon.com/lambda/latest/dg/configuration-layers.html)
[pyodbc documentation](https://github.com/mkleehammer/pyodbc/wiki)

Please make sure to refer to the above documentation for any additional information or troubleshooting.
