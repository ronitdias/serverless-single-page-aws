# serverless-single-page-aws
Create an AWS CloudFront distribution that serves static web content from S3 and routes API traffic to API Gateway.

Inspired from - https://github.com/MadSkills-io/fullstack-serverless

**:zap: Pros**

- Allows you to set-up custom domain for a S3 hosted site and API Gateway
- Free SSL using AWS CertificateManager
- No CORS needed
- Enables CDN caching of resources - so you don't waste Lambda invocations or API Gateway traffic
  for serving static files (just [set Cache-Control headers](https://serverless.com/framework/docs/providers/aws/events/apigateway/#custom-response-headers) in API responses)
- Much more CloudWatch statistics of API usage (like bandwidth metrics)
- Real world [access log](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/AccessLogs.html) - out of the box, API Gateway currently does not provide any kind of real "apache-like" access logs for your invocations
- [Web Application Firewall](https://aws.amazon.com/waf/) support - enable AWS WAF to protect your API from security threats
