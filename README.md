# Docker Auto Labels
[![](https://img.shields.io/pypi/v/auto-docker-labels.svg)](https://pypi.python.org/pypi/auto-docker-labels)

[![](https://img.shields.io/travis/khulnasoft/auto-docker-labels.svg)](https://travis-ci.org/khulnasoft/auto-docker-labels)


Automatically generate Docker Swarm mode node labels for each constraint label in each service in a Docker Compose / Docker Stack file.


## Description

This command line package is made to be used with a Docker Swarm mode cluster.

It will:
* Read a Docker Compose / Docker Stack file.
* Extract the node label constraints for each service.
* Check that all the labels exist in the Docker Swarm mode cluster.
* For each label that doesn't exist, create it in a random node in the cluster.

Adding label constraints helps you ensure that all the "stateful"
Docker services (like databases) are always deployed to the same
node (specially useful in a multi-node cluster).

This program will ensure that those labels exist in one node
in the cluster, if they don't exist, they are created in one
node chosen randomly.

That way, the first time you deploy a stack, a random node will be assigned
to each stateful service (by this command, right before the deployment).

And for all subsequent deployments, the stateful services will go to the
same nodes that they were using.

For examples on how to use it, check: https://github.com/khulnasoft/full-stack

## Release Notes

### Latest Changes

* init commit. PR [#1](https://github.com/khulnasoft/auto-docker-labels/pull/1) by [@gitworkflows](https://github.com/gitworkflows).

#### Internal

* 🔧 Add GitHub templates for discussions and issues, and security policy. PR [#9](https://github.com/khulnasoft/auto-docker-labels/pull/9) by [@alejsdev](https://github.com/alejsdev).
* 🔧 Add funding. PR [#8](https://github.com/khulnasoft/auto-docker-labels/pull/8) by [@khulnasoft](https://github.com/khulnasoft).
* 👷 Add latest-changes GitHub Action. PR [#6](https://github.com/khulnasoft/auto-docker-labels/pull/6) by [@khulnasoft](https://github.com/khulnasoft).
* 👷 Add dependabot. PR [#7](https://github.com/khulnasoft/auto-docker-labels/pull/7) by [@khulnasoft](https://github.com/khulnasoft).

### 0.2.3

## License

MIT License
