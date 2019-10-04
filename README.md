# Jenkins on DC/OS
[![Build Status](https://jenkins.mesosphere.com/service/jenkins/buildStatus/icon?job=Jenkins/public-jenkins-dcos-master)](https://jenkins.mesosphere.com/service/jenkins/view/Velocity/job/Jenkins/job/public-jenkins-dcos-master/)
[![Docker Stars](https://img.shields.io/docker/stars/mesosphere/jenkins.svg)][docker-hub]
[![Docker Pulls](https://img.shields.io/docker/pulls/mesosphere/jenkins.svg)][docker-hub]
[![](https://images.microbadger.com/badges/image/mesosphere/jenkins.svg)](http://microbadger.com/images/mesosphere/jenkins "Get your own image badge on microbadger.com")

Run a Jenkins master on DC/OS, using Docker and Nginx. This Jenkins instance is pre-configured to autoscale build agents onto the DC/OS cluster using the [Jenkins Mesos plugin][mesos-plugin].

## Overview
This repo contains a [Dockerfile](Dockerfile) that runs Jenkins inside a Docker
container and uses [Nginx][nginx-home] as a reverse proxy. It also provides
several Jenkins plugins and a basic Jenkins configuration in order to get you
up and running quickly with Jenkins on DC/OS.

## Reporting issues

Please report issues and submit feature requests for Jenkins on DC/OS by [creating an issue in the DC/OS JIRA][dcos-jira] (JIRA account required).

## Included in this repo
Base packages:

  * [Jenkins][jenkins-home] 2.190.1 (LTS)
  * [Nginx][nginx-home] 1.10.3

Jenkins plugins:
  * ace-editor:1.1
  * ansicolor:0.6.2
  * ant:1.10
  * antisamy-markup-formatter:1.6
  * apache-httpcomponents-client-4-api:4.5.10-1.0
  * artifactory:3.4.1
  * authentication-tokens:1.3
  * aws-credentials:1.28
  * aws-java-sdk:1.11.636
  * azure-commons:1.0.4
  * azure-credentials:1.6.1
  * azure-vm-agents:1.2.2
  * blueocean-autofavorite:1.2.4
  * blueocean-bitbucket-pipeline:1.19.0
  * blueocean-commons:1.19.0
  * blueocean-config:1.19.0
  * blueocean-core-js:1.19.0
  * blueocean-dashboard:1.19.0
  * blueocean-display-url:2.3.0
  * blueocean-events:1.19.0
  * blueocean-git-pipeline:1.19.0
  * blueocean-github-pipeline:1.19.0
  * blueocean-i18n:1.19.0
  * blueocean-jira:1.19.0
  * blueocean-jwt:1.19.0
  * blueocean-personalization:1.19.0
  * blueocean-pipeline-api-impl:1.19.0
  * blueocean-pipeline-editor:1.19.0
  * blueocean-pipeline-scm-api:1.19.0
  * blueocean-rest-impl:1.19.0
  * blueocean-rest:1.19.0
  * blueocean-web:1.19.0
  * blueocean:1.19.0
  * bouncycastle-api:2.17
  * branch-api:2.5.4
  * build-name-setter:2.0.3
  * build-timeout:1.19
  * cloud-stats:0.25
  * cloudbees-bitbucket-branch-source:2.5.0
  * cloudbees-folder:6.9
  * command-launcher:1.3
  * conditional-buildstep:1.3.6
  * config-file-provider:3.6.2
  * configuration-as-code:1.31
  * copyartifact:1.42.1
  * credentials-binding:1.20
  * credentials:2.3.0
  * cvs:2.14
  * display-url-api:2.3.2
  * docker-build-publish:1.3.2
  * docker-commons:1.15
  * docker-workflow:1.19
  * durable-task:1.30
  * ec2:1.46.1
  * embeddable-build-status:2.0.2
  * external-monitor-job:1.7
  * favorite:2.3.2
  * git-client:2.8.6
  * git-server:1.8
  * git:3.12.1
  * github-api:1.95
  * github-branch-source:2.5.8
  * github-organization-folder:1.6
  * github:1.29.4
  * gitlab-plugin:1.5.13
  * gradle:1.34
  * greenballs:1.15
  * handlebars:1.1.1
  * handy-uri-templates-2-api:2.1.7-1.0
  * htmlpublisher:1.21
  * ivy:2.1
  * jackson2-api:2.9.10
  * javadoc:1.5
  * jdk-tool:1.3
  * jenkins-design-language:1.19.0
  * jira:3.0.10
  * job-dsl:1.76
  * jobConfigHistory:2.24
  * jquery-detached:1.2.1
  * jquery-ui:1.0.2
  * jquery:1.12.4-1
  * jsch:0.1.55.1
  * junit:1.28
  * ldap:1.20
  * lockable-resources:2.5
  * mailer:1.29
  * mapdb-api:1.0.9.0
  * marathon:1.6.0
  * matrix-auth:2.4.2
  * matrix-project:1.14
  * maven-plugin:3.4
  * mercurial:2.8
  * metrics:4.0.2.6
  * momentjs:1.1.1
  * monitoring:1.79.0
  * nant:1.4.3
  * node-iterator-api:1.5.0
  * pam-auth:1.5.1
  * parameterized-trigger:2.35.2
  * pipeline-build-step:2.9
  * pipeline-github-lib:1.0
  * pipeline-graph-analysis:1.10
  * pipeline-input-step:2.11
  * pipeline-milestone-step:1.3.1
  * pipeline-model-api:1.3.9
  * pipeline-model-declarative-agent:1.1.1
  * pipeline-model-definition:1.3.9
  * pipeline-model-extensions:1.3.9
  * pipeline-rest-api:2.12
  * pipeline-stage-step:2.3
  * pipeline-stage-tags-metadata:1.3.9
  * pipeline-stage-view:2.12
  * plain-credentials:1.5
  * prometheus:2.0.6
  * pubsub-light:1.13
  * rebuild:1.31
  * role-strategy:2.14
  * run-condition:1.2
  * s3:0.11.2
  * saferestart:0.3
  * saml:1.1.3
  * scm-api:2.6.3
  * script-security:1.66
  * sse-gateway:1.20
  * ssh-agent:1.17
  * ssh-credentials:1.17.3
  * ssh-slaves:1.30.2
  * structs:1.20
  * subversion:2.12.2
  * timestamper:1.10
  * token-macro:2.8
  * translation:1.16
  * trilead-api:1.0.5
  * variant:1.3
  * windows-slaves:1.4
  * workflow-aggregator:2.6
  * workflow-api:2.37
  * workflow-basic-steps:2.18
  * workflow-cps-global-lib:2.15
  * workflow-cps:2.74
  * workflow-durable-task-step:2.34
  * workflow-job:2.35
  * workflow-multibranch:2.21
  * workflow-scm-step:2.9
  * workflow-step-api:2.20
  * workflow-support:3.3

## Packaging
Jenkins is available as a package in the [Mesosphere Universe][universe].
To make changes to the Jenkins package, submit a pull request against the
Universe.

## Installation

To install Jenkins for the DC/OS, simply run `dcos package install jenkins` or install via the Universe page in the DC/OS UI.

Jenkins should now be available at <http://dcos.example.com/service/jenkins>.
See [Getting Started][getting-started] for more in-depth instructions and
configuration options.

## Releasing
To release a new version of this package:

  1. Update [the Jenkins conf][jenkins-conf] to reference the current release of
  the [jenkins-dind][jenkins-dind] Docker image (if needed).
  2. Add some release notes to [CHANGELOG.md](CHANGELOG.md)
  3. Tag the commit on master that you want to be released.
  4. Once [the build][jenkins-build] has successfully completed, submit a new
  pull request against [the Universe][universe] referencing the new tag.

[dcos-jira]: https://jira.mesosphere.com/secure/CreateIssueDetails!init.jspa?pid=14110&issuetype=3
[docker-hub]: https://hub.docker.com/r/mesosphere/jenkins
[getting-started]: https://docs.mesosphere.com/service-docs/jenkins/quickstart/
[jenkins-conf]: /conf/jenkins/config.xml
[jenkins-dind]: https://github.com/mesosphere/jenkins-dind-agent
[jenkins-home]: https://jenkins-ci.org/
[mesos-plugin]: https://github.com/jenkinsci/mesos-plugin
[nginx-home]: http://nginx.org/en/
[jenkins-build]: https://jenkins.mesosphere.com/service/jenkins/job/public-jenkins-dcos-master/
[universe]: https://github.com/mesosphere/universe
