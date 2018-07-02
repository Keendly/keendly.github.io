
> #WARNING# This is a technical overview of Keendly, a service that lets you deliver articles from RSS aggregators to a Kindle device. The service was shut down on the 2nd of July 2018 and is no longer working.

### Architecture
Keendly ran on AWS heavily utilizing services it provides. Main services used were:
* **Lambda** - heavily used across system, both for the API and almost all steps of the delivery pipeline
* **Step Functions** - for the [delivery pipeline](https://github.com/Keendly/delivery-state-machine)
* **S3** - serving [Keendly App](https://github.com/Keendly/keendly-app), [Blog](https://github.com/Keendly/blog.keendly) and [main site](https://github.com/Keendly/keendly.com), intermediate storage for delivery
* **API Gateway** - exposing [Keendly API](https://github.com/Keendly/keendly-api) to the world
* **Cloudwatch** - events for scheduled deliveries + alarms, dashboards and logs
* **RDS** - just a database
* **ECS** - to run whatever couldn't run in Lambda
* **Cloudfront** - CDN

![Diagram](https://octodex.github.com/images/yaktocat.png)

### Some numbers about Keendly

### 2015 - registered users
### 1181 - users that used Keendly at least once
### 57932 - ebooks delivered
### 9665 - unique feeds delivered
