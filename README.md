[![Go Report Card](https://goreportcard.com/badge/github.com/chen-keinan/mesh-kridik)](https://goreportcard.com/report/github.com/chen-keinan/mesh-kridik)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/chen-keinan/lxd-probe/blob/main/LICENSE)
[![Build Status](https://travis-ci.com/chen-keinan/mesh-kridik.svg?branch=master)](https://travis-ci.com/chen-keinan/mesh-kridik)
<img src="./pkg/img/coverage_badge.png" alt="test coverage badge">
# mesh-kridik
Scan your Kubernetes service mesh security !!

mesh-kridik is an open-source security scanner that performs various security checks on a Kubernetes istio service mesh and outputs a security report.

The security checks tests are the full implementation of [istio security best practices](https://istio.io/latest/docs/ops/best-practices/security/) <br>

The security checks performed on a Kubernetes cluster with istio service mesh, and the output audit report includes:
the root cause of the security issue  and proposed remediation for the security issue


* [Installation](#installation)
* [Quick Start](#quick-start)
* [Istio Security Checks](#istio-security-checks)



## Installation

```shell
git clone https://github.com/chen-keinan/mesh-kridik
cd mesh-kridik
make build
```

- Note: kube-beacon require root user to be executed

## Quick Start

Execute Mesh-Kridik without any flags , execute all tests
```shell
 ./mesh-kridik 

```

Execute mesh-kridik  with flags , execute test on demand

```shell
Usage: mesh-kridik [--version] [--help] <command> [<args>]

Available commands are:
  -r , --report :  run audit tests and generate remediation report
 ```

Execute tests and generate failure tests report

```
./mesh-kridik -r
```

## Istio Security Checks
<table style="width:600px">
<tr>
    <th style="width:100px">Name</th>
    <th style="width:200px">Description</th>
    <th style="width:300px">impact</th>
</tr>
<tr>
    <td > Mutual TLS </td>
    <td > Istio  Mutual TLS proxies are configured in permissive mode by default </td>
    <td> proxies will accept both mutual TLS and plaintext traffic</td>
</tr>
</table>
