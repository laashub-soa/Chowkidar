# Chowkidar

[![Go Report Card](https://goreportcard.com/badge/github.com/stakater/chowkidar?style=flat-square)](https://goreportcard.com/report/github.com/stakater/chowkidar)
[![Go Doc](https://img.shields.io/badge/godoc-reference-blue.svg?style=flat-square)](http://godoc.org/github.com/stakater/chowkidar)
[![Release](https://img.shields.io/github/release/stakater/chowkidar.svg?style=flat-square)](https://github.com/stakater/chowkidar/releases/latest)
[![Build Status](https://travis-ci.org/stakater/chowkidar.svg?branch=master)](https://travis-ci.org/stakater/chowkidar)
[![Coverage Status](https://coveralls.io/repos/github/stakater/chowkidar/badge.svg?branch=master)](https://coveralls.io/github/stakater/chowkidar?branch=master)
[![GitHub tag](https://img.shields.io/github/tag/stakater/chowkidar.svg?maxAge=86400)](https://github.com/stakater/chowkidar)
[![Docker Pulls](https://img.shields.io/docker/pulls/stakater/chowkidar.svg)](https://hub.docker.com/r/stakater/chowkidar/)
[![Docker Stars](https://img.shields.io/docker/stars/stakater/chowkidar.svg)](https://hub.docker.com/r/stakater/chowkidar/)
[![MicroBadger Layers Size](https://images.microbadger.com/badges/image/stakater/chowkidar.svg)](https://microbadger.com/images/stakater/chowkidar)
[![license](https://img.shields.io/github/license/stakater/chowkidar.svg)](LICENSE)

## WHY NAME CHOWKIDAR?
Chowkidar, an Urdu word, is used for Security Guards in Pakistan. This Chowkidar will stand guard your cluster and will look for any anomaly in the cluster and will act as you want it to.

## Problem
We would like to watch for relevant events happening inside kubernetes and then perform actions depending upon the criteria.
e.g. I would like to get a slack notification when a pod is submitted without requests & limits.

## Solution

Chowkidar allows you to have multiple controllers that will continuously watch types in all the namespaces and automatically perform any actions given in the yaml file. With this, you can easily check for any criteria on your Pods/other types and take corresponding actions.

## Deploying to Kubernetes

### Vanilla Manifests

You have to first clone or download the repository contents. The kubernetes deployment and files are provided inside `deployments/kubernetes/manifests` folder.

### Configuring

First of all you need to modify `configs/config.yaml` file. Following are the available options that you can use to customize the controllers:

| Key                   |Description                                                                    |
|-----------------------|-------------------------------------------------------------------------------|
| type                  | The type of Resource you want to monitor, like Pods, Deployments, etc         |
| watchcriterion        | The criterion for which you want to take actions for the controller e.g. ResourceExists,etc     |
| actions               | The Array of actions that you want to take, e.g. send message to Slack, etc   |

### Supported Types
Currently we are supporting, 
- Pods


We will be adding support for other Types as well in the future

### Supported Actions
Currently we are supporting following Actions with their Parameters,
- Slack: you need to provide `token` and `Channel Name` as Parameters in the yaml file

We will be adding support for other Actions as well in the future

#### Deploying

You can deploy Chowkidar by running the following kubectl commands:

```bash
kubectl apply -f configmap.yaml -n <namespace>
kubectl apply -f rbac.yaml -n <namespace>
kubectl apply -f deployment.yaml -n <namespace>
```

### Helm Charts

Or alternatively if you configured `helm` on your cluster, you can deploy Chowkidar via helm chart located under `deployments/kubernetes/chart/Chowkidar` folder.

## Help

**Got a question?**
File a GitHub [issue](https://github.com/stakater/Chowkidar/issues), or send us an [email](mailto:stakater@gmail.com).

### Talk to us on Slack
Join and talk to us on the #tools-imc channel for discussing Chowkidar

[![Join Slack](https://stakater.github.io/README/stakater-join-slack-btn.png)](https://stakater-slack.herokuapp.com/)
[![Chat](https://stakater.github.io/README/stakater-chat-btn.png)](https://stakater.slack.com/messages/CA66MMYSE/)

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/stakater/Chowkidar/issues) to report any bugs or file feature requests.

### Developing

PRs are welcome. In general, we follow the "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull request** so that we can review your changes

NOTE: Be sure to merge the latest from "upstream" before making a pull request!

## Changelog

View our closed [Pull Requests](https://github.com/stakater/Chowkidar/pulls?q=is%3Apr+is%3Aclosed).

## License

Apache2 © [Stakater](http://stakater.com)

## About

`Chowkidar` is maintained by [Stakater][website]. Like it? Please let us know at <hello@stakater.com>

See [our other projects][community]
or contact us in case of professional services and queries on <hello@stakater.com>

  [website]: http://stakater.com/
  [community]: https://github.com/stakater/