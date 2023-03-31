# lacework-hydrate-alerts
Lacework webhook lambda function to hydrate alerts through the API Details endpoint    This lambda function leverages the LaceworkSDK to interact with the LaceworkAPI

## Deployment Guide
Open your AWS console, navigate to the CloudFormation console and select Create Stack

Add the following URL as the template and click Next:
https://craig-labfun-lwcs-lacework-eks.s3.us-west-1.amazonaws.com/lambd-webhook-code/LaceworkWebhookFilter.yaml

Provide values for the following environement variables:
- webhookurl :: destination webhook url
- token :: authorization token via destination webhook 
- LwAccount :: account name via lacework api token
- LwApiKey :: api key via lacework api token
- LwApiSecret :: api secret via via lacework api token


Click Next until the Webhook has been deployed

Find the created Lambda Function in the AWS Console and copy the function URL

Create an Alert Channel in the Lacework UI and paste the Lambda URL

Create an Alert Rule in the Lacework UI to customize which alerts will be hydrated by the Lambda

Test the Alert Channel Intrgration to confirm it is configured properly

