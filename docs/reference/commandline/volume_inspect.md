<!--[metadata]>
+++
title = "volume inspect"
description = "The volume inspect command description and usage"
keywords = ["volume, inspect"]
[menu.main]
parent = "smn_cli"
+++
<![end-metadata]-->

# volume inspect

    Usage: docker volume inspect [OPTIONS] VOLUME [VOLUME...]

    Inspect one or more volumes

    -f, --format=       Format the output using the given go template.
    --help=false        Print usage

Returns information about a volume. By default, this command renders all results
in a JSON array. You can specify an alternate format to execute a given template
is executed for each result. Go's
[text/template](http://golang.org/pkg/text/template/) package describes all the
details of the format.

Example output:

    $ docker volume create
    85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d
    $ docker volume inspect 85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d
    [
      {
          "Name": "85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d",
          "Driver": "local",
          "Mountpoint": "/var/lib/docker/volumes/85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d/_data"
      }
    ]

    $ docker volume inspect --format '{{ .Mountpoint }}' 85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d
    "/var/lib/docker/volumes/85bffb0677236974f93955d8ecc4df55ef5070117b0e53333cc1b443777be24d/_data"
