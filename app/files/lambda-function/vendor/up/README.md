<!-- note marker start -->
NOTE: This repo contains only the documentation for the private BoltsOps repo code.
Original file: https://github.com/boltops-pro/upcheck/blob/master/app/files/lambda-function/vendor/up/README.md
The docs are publish so they are available for interested subscribers.
For access to the source code, you can become a BoltOps subscriber.
See: https://learn.boltops.com

<!-- note marker end -->

# Up

![](https://img.boltops.com/boltopspro/blueprints/upcheck/up-check-cloudwatch.png)

The `up` command checks if services are up and running and reports CloudWatch custom metrics.  It's a companion tool that is used by the [UpCheck Blueprint](https://github.com/boltopspro/upcheck).

* Metric Names: 1) HealthCheckStatus and 2) ResponseTime
* Useful to run this script within the network to check internal applications that cannot be pinged from the outside world.
* Tool reads a `up.yml` file in the current directory by default.

## Usage

    up check

The tool looks for a configuration file in these locations:

1. up.yml - current directory
2. config/up.yml - current directory
3. ~/.up.yml - home directory (note the dot)

The up.yml looks like this:

```yaml
---
- name: demo-web-1
  url: http://external-site.com/health/check/path
- name: demo-web-2
  url: http://internal-site.private/
```

### Environment Variables

Some of the tool's settings can be controlled with environmental variables:

Env Var | Description | Default Value
--- | --- | ---
UP\_CLOUDWATCH\_DIMENSION\_NAME | CloudWatch metric dimension name | App
UP\_CLOUDWATCH\_DIMENSION\_VALUE | CloudWatch metric dimension value | site name from `up.yml`
UP\_CLOUDWATCH\_ENABLED | Enables sending of the data to CloudWatch. | (unset)
UP\_CLOUDWATCH\_NAMESPACE | CloudWatch metric namespace | UpCheck
UP\_MAX\_THREADS | Max number of threads | 200

## Installation

To install:

    rake install
