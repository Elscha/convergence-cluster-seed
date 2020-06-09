<div align="center">
  <img alt="Convergence Logo" height="80" src="https://convergence.io/assets/img/convergence-logo.png" >
</div>

# Convergence Cluster Seed
[![Build Status](https://travis-ci.org/convergencelabs/convergence-cluster-seed.svg?branch=master)](https://travis-ci.org/convergencelabs/convergence-cluster-seed)

This project contains the Convergence Cluster seed. It is a lightweight [Akka](https://akka.io/) cluster node that can be used to bootstrap the cluster. The project contains almost no code other than that required to start up the akka cluster. This makes it very unlikely that the node will crash, and minimizes the amount of memory needed to maintain reliable cluster seed nodes.

## Building
The project can be built using the build script:

```shell script
scripts/build.sh
```

## Running
- `CLUSTER_SEED_NODES`: A comma separated list of seed nodes. For example `host1,host2`
- `AKKA_LOG_LEVEL`: A Log4J Log Level such as `INFO`, `DEBUG`
- `EXTERNAL_HOSTNAME`: The hostname that external hosts will connect to the cluster seed. Required if the cluster seed is behind a proxy, or deployed in a docker environment like Kubernetes.

To run the container execute the following command:

```shell script
docker run --rm \
  --publish 2551:2551 \
  --env CLUSTER_SEED_NODES="localhost" \
  --env EXTERNAL_HOSTNAME="localhost" \
  convergencelabs/convergence-cluster-seed
```

## Support
[Convergence Labs](https://convergencelabs.com) provides several different channels for support:

- Please use the [Convergence Community Forum](https://forum.convergence.io) for general and technical questions, so the whole community can benefit.
- For paid dedicated support or custom development services, [contact us](https://convergence.io/contact-sales/) directly.
- Chat with us on the [Convergence Public Slack](https://slack.convergence.io).
- Email <support@convergencelabs.com> for all other inquiries.

## License
The Convergence Server is licensed under the [GNU Public License v3](LICENSE) (GPLv3) license. Refer to the [LICENSE](LICENSE) for the specific terms and conditions of the license.

The Convergence Server is also available under a Commercial License. If you are interested in a non-open source license please contact us at [Convergence Labs](https://convergencelabs.com).