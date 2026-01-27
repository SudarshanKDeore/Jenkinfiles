## Used parameters:

```
ENV (dev / preprod / prod)
BRANCH (Git branch)
VERSION (artifact version / image tag)
RUN_TESTS (true/false)
DEPLOY (true/false)
DOCKER_IMAGE (image name)
```

## How this works in production:
## When you click Build with Parameters, Jenkins asks:
```
ENV → dev / preprod / prod
BRANCH → which branch to build
VERSION → Docker tag
RUN_TESTS → run tests or skip
DEPLOY → deploy or just build
DOCKER_IMAGE → image name
```

## Typical production usage:
```
| Scenario        | Values                                    |
| --------------- | ----------------------------------------- |
| CI Build        | DEPLOY=false                              |
| Dev deploy      | ENV=dev, DEPLOY=true                      |
| Preprod release | ENV=preprod, VERSION=1.2.5                |
| Prod release    | ENV=prod, RUN_TESTS=false, VERSION=stable |
```

## Interview one-liner:
```
“In production Jenkins pipelines we use parameterized builds to select environment,
              branch, version, and deployment flags at runtime.
This gives flexibility and control without changing the Jenkinsfile.”
```

## SNS Body:
```
Subject: Jenkins SUCCESS: applicationmgmt-pipeline

Job: applicationmgmt-pipeline
Build: #45
Status: SUCCESS
Environment: prod
Version: 1.2.3
URL: http://jenkins/job/applicationmgmt-pipeline/45/
```
