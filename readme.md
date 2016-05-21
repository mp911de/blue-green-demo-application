Blue/Green Deployments to Pivotal Cloud Foundry using Gradle
============================================================

This repository contains the reference code to the blog post
[Blue/Green Deployments to Pivotal Cloud Foundry using Gradle](http://www.paluch.biz/blog/164-blue-green-deployments-to-pivotal-cloud-foundry-using-gradle.html).

The deployment script features:

* Blue/Green deployment to production
* Single-instance deployment to other spaces/stages
* Stage-discovery from the branch name when using TravisCI
   * Builds on `master` are deployed to production
   * Builds on branches beginning with `stage-` are deployed to the staging space
   * PR builds can be also built but don't get deployed at all.
   * This script assumes that forks does not get deployed as forks may inherit the TravisCI build but only the master build has build env variables set up that provide login credentials to CloudFoundry
* Manual build run


## Building and Deploying with TravisCI

`./gradle deploy`

## Building and Deploying from your local machine

`./gradle deploy -Pspace=<targetspace>`