# aws_lambda_function_to_azure_log_analytics

> A lambda function that sends logs to azure-log-analytics


```
+--------+     +---------------------+
 Lambda +---> | Azure Log Analytics |
+--------+     +---------------------+
```

## Deploying the function

Lambda requires you to include any npm dependencies your function needs with the bundle. Prepare the zip bundle:

```sh
$ npm install --production
$ zip -r lambda-bundle.zip *
```

Then upload the bundle directly to Lambda through the upload button

<img width="708" alt="" src="https://user-images.githubusercontent.com/717076/34253019-8ed0936c-e64e-11e7-82e5-a464bdf508ac.png">

## Usage

The function expects several environment variables to be set:

- `WORKSPACEID` - WorkspaceID is the unique identifier for the Log Analytics workspace.
- `SHAREDKEY` - Primary Key ID of Log Analytics workspace.
- `APIVERSION` - The version of the API to use with this request. Currently, it's `2016-04-01`.
- `PREFIX` - The index name prefix. For example, if `PREFIX='aws_logs'`
  > Note: Index name do not allow hyphen(-).
