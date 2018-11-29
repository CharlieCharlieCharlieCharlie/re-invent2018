# DEV309 CI/CD For Serverless and Containerized Applications

* Lambda & Fargate

* Source >  Build > Test > Production
* CI/CD encourages:
  * frequent deployments
  * shorter change lead time
  * less change failure rates
  * quicker post mortems and DR
* 48% of software teams embrace CI/CD with optimal results

## CodePipeline

* Code Commit / Github / S3 as a source
* AWS CodePipeline uses ECR as pipeline source
* Triggers on Cloudwatch events or AWS Health events
* Triggers on webhooks

## Code Deploy

* Can use weighted lambdas to route traffic.
* Canary alarms can do automatic rollback.
* I.e. shift 10% traffic to new version lambda, wait 10 minutes, if no errors then fully deploy, otherwise fully rollback.
* Can do blue green in ECS and Fargate.

## Infrastructure as code

* Build stage - validate an artifact
  * unit tests
  * mocked services
* Test phase - validate an environment