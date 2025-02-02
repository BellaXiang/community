![logo-contribution](https://user-images.githubusercontent.com/6755791/33362307-d5e59a16-d516-11e7-86df-a0dfdfee7b88.jpg)

# Contribution Guide

TiDB is a community driven open source project and we welcome any contributor.
The process of contributing to the TiDB project may be different than many
other projects you have been involved in. This document outlines some
conventions about development workflow, commit message formatting, contact
points and other resources to make it easier to get your contribution accepted.
This document is the canonical source of truth for things like supported
toolchain versions for building and testing TiDB.

## What is a Contributor?

A Contributor refers to the person who contributes to the following projects:
- TiDB: https://github.com/pingcap/tidb
- TiKV: https://github.com/pingcap/tikv
- TiSpark: https://github.com/pingcap/tispark
- PD: https://github.com/pingcap/pd
- Docs: https://github.com/pingcap/docs
- Docs-cn: https://github.com/pingcap/docs-cn

## How to become a TiDB Contributor?

If a PR (Pull Request) submitted to the TiDB/TiKV/TiSpark/PD/Docs/Docs-cn
projects by you is approved and merged, then you become a TiDB Contributor.

You are also encouraged to participate in the projects in the following ways:
- Actively answer technical questions asked by community users.
- Help to test the projects.
- Help to review the pull requests (PRs) submitted by others.
- Help to improve technical documents.
- Submit valuable issues.
- Report or fix known and unknown bugs.
- Participate in the existing discussion about features in the roadmap, and have interest in implementing a certain feature independently.
- Write articles about the source code analysis and usage cases for the projects.

## Pre submit pull request/issue flight checks

Before you move on, please make sure what your issue and/or pull request is, a
simple bug fix or an architecture change.

In order to save reviewers' time, each issue should be filed with template and
should be sanity-checkable in under 5 minutes.

### Is this a simple bug fix?

Bug fixes usually come with tests. With the help of continuous integration
test, patches can be easy to review. Please update the unit tests so that they
catch the bug! Please check example
[here](https://github.com/pingcap/tidb/pull/2808).

### Is this an architecture improvement?

Some examples of "Architecture" improvements:

- Converting structs to interfaces.
- Improving test coverage.
- Decoupling logic or creation of new utilities.
- Making code more resilient (sleeps, backoffs, reducing flakiness, etc).

If you are improving the quality of code, then justify/state exactly what you
are 'cleaning up' in your Pull Request so as to save reviewers' time. An
example will be this [pull request](https://github.com/pingcap/tidb/pull/3113).

If you're making code more resilient, test it locally to demonstrate how
exactly your patch changes things.

## Building TiDB on a local OS/shell environment

TiDB development only requires `go` set-up. If you already have, simply type
`make` from terminal.

### Go

TiDB is written in [Go](http://golang.org).
If you don't have a Go development environment,
please [set one up](http://golang.org/doc/code.html).

The version of GO should be **1.13** or above.

After installation, there are two ways to build TiDB binary.

#### For a quick taste

The `GOPATH` is not necessary.

```
mkdir tmp
cd tmp
echo 'module tidb' > go.mod
GO111MODULE=on go get github.com/pingcap/tidb@c385cbdcca83eeed283139814a7ea149e3116e66
GO111MODULE=on go build -o tidb-server github.com/pingcap/tidb/tidb-server
```

The `c385cbdcca83eeed283139814a7ea149e3116e66` can be changed to any other commit hash. Try the latest commit hash [here](https://github.com/pingcap/tidb/commits/master).

#### For development

You'll need `GOPATH` defined, and `PATH` modified to access your Go binaries.

A common setup is the following but you could always google a setup for your own flavor.

```sh
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
```

Then you can use `make` command to build TiDB.

#### Dependency management

TiDB uses [`Go Modules`](https://github.com/golang/go/wiki/Modules) to manage dependencies.

## Reviewer

Reviewers are able to review code for quality and correctness on some part of a subproject. They are knowledgeable about both the codebase and software engineering principles.

### How to become a reviewer?

* Knowledgeable about the codebase
* Sponsored by 2 Committers
* merged at least 20 PRs 

### Responsibilities and privileges

* Responsible for project quality control
    * Focus on code quality and correctness, including testing and factoring 
    * May also review for more holistic issues
* Expected to be responsive to review PR on time
* Assigned test and fix bugs in subproject 
* Have the rights to approve PR
* Participate in the future seminar

## Workflow

See the [Github Workflow](https://github.com/pingcap/community/blob/master/contributors/workflow.md)

## Code style

The coding style suggested by the Golang community is used in TiDB. See the
[style doc](https://github.com/golang/go/wiki/CodeReviewComments) for details.

## Commit message and Pull Request style

See the [Commit Message and Pull Request Style](https://github.com/pingcap/community/blob/master/commit-message-pr-style.md)
