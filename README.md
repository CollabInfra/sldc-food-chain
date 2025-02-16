# sldc-food-chain
Example on how to build, deploy and observe two apps in a complete SDLC chain

Main goal: install OWAPS WebGoat and example-voting-app in AWS, Rancher Desktop (local k8s), OVH and LeaseWeb and other providers, with a full DevSecOps/SDLC cycle

The sub goal is to evaluate many tools for each "step", to see which ones detect problems and other issues (code quality, etc), while checking which tools reports too much information on their backend.

* Planning
  * Jira

* Defect management
  * Xray for Jira

* Source code
  * GitHub
  * Bitbucket
  * GitLab
  * Linters and pre-commit

* Build tools
  * TeamCity
  * GitHub Actions
  * GitLab Pipelines
  * Azure Pipelines
  * Jenkins

* Deployment tools
  * GitHub Actions
  * GitLab Pipelines
  * Azure Pipelines
  * Argo CD
  * Jenkins

* Obervability
  * CloudWatch (Logs, Metrics, Xray)
  * Datadog
  * OpenMetrics, OpenTelemetry, Jaeger and Grafana Cloud

* Service Catalog
  * Backstage
  * Datadog
  * Atlassian Compass

* SAST
  * semgrep
  * GitHub
  * GitLab
  * Snyk
  * SonarQube
  * Veracode

* Cost management
  * Infracost
  * Datadog

* DAST
  * Aikido DAST
  * Invicti
  * Zed Attack Proxy

* Docker image scanning
    * Snyk
    * trivy
    * ECR
    * inspec
    * docker-bench-security
    * docker scout
    * aquasec
    * JFrog Xray

* Artifacts management
  * ECR
  * JFrog Artifactory

* Load/stress and integration testing

* Secret management

* Key management
  * AWS KMS

* Other
  * Karpenter
  * OIDC
  * AWS Security Hub

* Terraform providers
    * https://registry.terraform.io/providers/LeaseWeb/leaseweb/latest
    * https://registry.terraform.io/providers/ovh/ovh/latest/docs
    * https://registry.terraform.io/providers/JetBrains/teamcity/latest/docs/resources/project
    * https://registry.terraform.io/providers/microsoft/azuredevops/latest/docs
    * https://registry.terraform.io/providers/taiidani/jenkins/latest/docs
    * https://registry.terraform.io/providers/DrFaust92/bitbucket/latest/docs
    * https://registry.terraform.io/providers/gitlabhq/gitlab/latest/docs
    * https://registry.terraform.io/providers/integrations/github/latest/docs
    * https://registry.terraform.io/providers/oboukili/argocd/latest/docs
