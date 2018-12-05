# Prometheus

This is a tutorial on how to launch and manage a fully working Prometheus cluster in AWS.

The notes are also posted on the [NETBEARS](https://netbears.com/blog/monitoring-alerting-prometheus-aws/) company blog. You might want to check the website out for more tutorials like this.

## What is Consul?

[Prometheus](https://prometheus.io/docs/introduction/overview/) is an open-source systems monitoring and alerting toolkit originally built at SoundCloud. Since its inception in 2012, many companies and organizations have adopted Prometheus, and the project has a very active developer and user community. It is now a standalone open source project and maintained independently of any company. To emphasize this, and to clarify the project's governance structure, Prometheus joined the Cloud Native Computing Foundation in 2016 as the second hosted project, after Kubernetes.

Prometheus's main features are:
1 a multi-dimensional data model with time series data identified by metric name and key/value pairs
2 a flexible query language to leverage this dimensionality
3 no reliance on distributed storage; single server nodes are autonomous
4 time series collection happens via a pull model over HTTP
5 pushing time series is supported via an intermediary gateway
6 targets are discovered via service discovery or static configuration
7 multiple modes of graphing and dashboarding support

## Deploy the stack

### Run the CloudFormation template in the AWS Console
* Login to the AWS console and browse to the CloudFormation section
* Select the cloudformation-template.yaml file
* Before clicking "Create", make sure that you scroll down and tick the “I acknowledge that AWS CloudFormation might create IAM resources” checkbox
* ...drink coffee...
* Go to the URL in the output section for the environment that you want to access

### Main resources created

* 1 AutoScaling Group
* 1 Elastic Load Balancer
* 1 DNS record (for ease of access)

### Monitoring

The stack launches [NodeExporter](https://github.com/prometheus/node_exporter/) (Prometheus exporter for hardware and OS metrics exposed by NIX kernels, written in Go with pluggable metric collectors) on each host inside the cluster.

## Final notes
Need help implementing this?

Feel free to contact us using [this form](https://netbears.com/#contact-form).
