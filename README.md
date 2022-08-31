# appsync-ws-api

This AppSync example demonstrate end-to-end implementations of a simple application using AWS AppSync resolvers integration with multiple datasources.
The example uses AWS AppSync as the front door to the client application. The client application(s) will only need to use a single GraphQL API request to send a GraphQL query to AWS AppSync. 
In AppSync you will define the schema and resolvers. AppSync resolvers are functions that convert the GraphQL payload to the underlying storage/target service using VTL (Velocity Template Mapping).

The sample uses a fictitious soccer club/players application where the end user can query their favorite soccer players, rank them and update their team score. In this use case, we will demosntrate 
three intergation scenarios using AppSync APIs

    1- Intergate using DynamoDB resolvers to retrieve favorite soccer player names andor top 10 soccer players in the world
    2- Websocket integration to demostarte an "out of band" initiation of a message where a message producer places a message on SQS and AppSync resolvers fetch the message from the queue and return to the client application.
    3- Intergate with Amazon RDS using a custom AppSync resolver (Lambda function) and return data requested by the client application
    
The sample application will use a serverless approach that align with AWS serverless best practices
    1- Solution delpoyed using CI/CD pipeline that include CodePipeline, AWS CodeCommit, and AWS CodeBuild
    2- IaC using SAM and CDK approaches
    3- Observability: Logging & Monitoring using CloudWatch and XRAY. Including CloudWatch alarms and dashbaord.
    4- Automated unit and integration testing
    5- Gloabl deployment using Amazon CloudFront
    6- Security using IAM/Cognito
    
The servcies used by this sample application include: 
    - AWS AppSync - front end that to serve client GraphQL API requests
    - DynamoDB - A NSQL database to store soccer players data
    - IAM - roles and permissions for different AWS services included in the solution
    - CloudFront - To scale the application globally and improve performance
    - S3- Object storage for static assets (html/CSS, etc.) for the front end
    - Lambda - Lambda functions used as a custom AppSync resolver to access Amazon RDS
    - RDS - A SQL database to store soccer clubs ratings and scores
    - SQS- message queuing to receive message from a message producer. Message will be sent to the client via AppSync
    - CloudWatch- For logging and monitoring
    - XRAY- For tracing and troubleshooting
    - SAM - For IaC to automate solution deployment
    
## Architecture

![Architecture diagram](./assets/initial Architecture.png)

 ## Observability configurations
  <Place holder>

![CloudWatch Dashboard](./assets/Dashboard.png)

## Testing  
< Place Holder>