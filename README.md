# Nexus IQ Webhook Reference Implementation

This is a reference implementation for consuming webhooks via [serverless](https://serverless.com/). In this 
implementation, a Nexus IQ Application Policy Evaluation webhook is consumed, validated and a message is sent to a Slack 
channel.

# Running Locally- edit test

The serverless offline plugin is installed to allow for local development. The application can be run using

```
sls offline start
```

after installing serverless and the node dependencies.

```
npm install serverless -g
npm install
```

# Configuration

Webhooks must be configured in Nexus IQ Server to point towards the endpoint generated by the serverless application. 
Information about configuring Nexus IQ Webhooks is available in 
[IQ Server Webhooks](https://help.sonatype.com/display/NXIQ/IQ+Server+Webhooks).

Environmental variables for the Slack Webhook URL and Nexus IQ Webhook secret key must be set in the 
[serverless configuration](serverless.yml).

# Unit Tests

Unit tests can be run with mocha using

```
npm test
```   

# Deploying to the Cloud

Information about deploying serverless applications to various cloud providers in available in the 
[serverless documentation](https://serverless.com/framework/docs/). If using AWS, for example, you must [configure
your credentials](https://serverless.com/framework/docs/providers/aws/guide/credentials/) and then deploy via 
`sls deploy`. Consideration should be taken as to the cost of running this service as well as the scope of the
handler as described in [serverless.yml](serverless.yml) and [index.js](index.js).
