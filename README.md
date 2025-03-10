# AWS Command Line Interface v2 on OpenBSD

This repo contains code which will allow you to build and install the
[AWS CLIv2](https://aws.amazon.com/cli/) on OpenBSD using the OpenBSD
[ports system](https://www.openbsd.org/faq/ports/ports.html).

For more information, read the blog post
[AWS CLIv2 on OpenBSD](https://www.packetmischief.ca/2023/08/16/awscliv2-on-openbsd/).

The ports in this repo are tested on OpenBSD 7.5 and 7.6 using the amd64 and arm64
architectures.

## Installation

To install the AWS CLIv2 port:

1 - Clone the repository from GitHub:

```text
git clone https://github.com/knightjoel/awscliv2-on-openbsd
```

2 - Copy the contents of the repo's `ports/` directory to `/usr/ports` (or
wherever your ports tree is).

```text
cd awscliv2-on-openbsd/ports
cp -a * /usr/ports
```

3 - Install some packages needed to build the port. You could allow ports to build and
install this software, but installing the packages will reduce the build time.

```text
doas pkg_add cmake python%3 ninja
```

4 - Install the AWS CLIv2 port.

If you have v1 of the AWS CLI installed, you'll have to uninstall it first.

```text
doas pkg_delete awscli
cd /usr/ports/sysutils/awscliv2
make install
```

5 - Verify installation

```text
% aws --version
aws-cli/2.24.20 Python/3.11.10 OpenBSD/7.6 source/amd64
```
