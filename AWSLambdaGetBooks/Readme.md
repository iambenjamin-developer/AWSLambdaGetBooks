# AWS Lambda Empty Function Project

This starter project consists of:
* Function.cs - class file containing a class with a single function handler method
* aws-lambda-tools-defaults.json - default argument settings for use with Visual Studio and command line deployment tools for AWS

You may also have a test project depending on the options selected.

The generated function handler is a simple method accepting a string argument that returns the uppercase equivalent of the input string. Replace the body of this method, and parameters, to suit your needs. 

## Here are some steps to follow from Visual Studio:

To deploy your function to AWS Lambda, right click the project in Solution Explorer and select *Publish to AWS Lambda*.

To view your deployed function open its Function View window by double-clicking the function name shown beneath the AWS Lambda node in the AWS Explorer tree.

To perform testing against your deployed function use the Test Invoke tab in the opened Function View window.

To configure event sources for your deployed function, for example to have your function invoked when an object is created in an Amazon S3 bucket, use the Event Sources tab in the opened Function View window.

To update the runtime configuration of your deployed function use the Configuration tab in the opened Function View window.

To view execution logs of invocations of your function use the Logs tab in the opened Function View window.

## Here are some steps to follow to get started from the command line:

Once you have edited your template and code you can deploy your application using the [Amazon.Lambda.Tools Global Tool](https://github.com/aws/aws-extensions-for-dotnet-cli#aws-lambda-amazonlambdatools) from the command line.

Install Amazon.Lambda.Tools Global Tools if not already installed.
```
    dotnet tool install -g Amazon.Lambda.Tools
```

If already installed check if new version is available.
```
    dotnet tool update -g Amazon.Lambda.Tools
```

Execute unit tests
```
    cd "AWSLambdaGetBooks/test/AWSLambdaGetBooks.Tests"
    dotnet test
```

Deploy function to AWS Lambda
```
    cd "AWSLambdaGetBooks/src/AWSLambdaGetBooks"
    dotnet lambda deploy-function
```

Get  Books
```
    dotnet lambda invoke-function GetBooks --payload "{}"   
```
```
[
  {
    "title": "Cuentos para pensar",
    "author": "Jorge Bucay",
    "published": "1997-03-01T10:15:30.1234567Z"
  },
  {
    "title": "La sombra del viento",
    "author": "Carlos Ruiz Zafón",
    "published": "2001-04-12T08:45:00.9876543Z"
  },
  {
    "title": "Rayuela",
    "author": "Julio Cortázar",
    "published": "1963-06-28T14:20:10.4567890Z"
  },
  {
    "title": "Los detectives salvajes",
    "author": "Roberto Bolaño",
    "published": "1998-02-01T17:00:00.0000000Z"
  },
  {
    "title": "El amor en los tiempos del cólera",
    "author": "Gabriel García Márquez",
    "published": "1985-09-05T22:10:05.7654321Z"
  }
]
```