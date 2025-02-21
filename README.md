# It Works In My Devcontainer

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/jvanbuel/it-works-in-my-devcontainer)

Devcontainers are (supposedly) standardized, reproducible development environments that can be shared with others. This repository is a collection of devcontainer configurations that behave differently when running them locally vs. running them in GitHub Codespaces.

1. [dockerComposeFile](#dockercomposefile)
2. [tmp-mount](#tmp-mount)

## dockerComposeFile

The `dockerComposeFile` attribute of the devcontainer specification allows you to specify one or more Docker Compose files to use when starting the devcontainer. This is useful for defining multi-container development environments, with one container being the primary development environment and the other containers being services (e.g. databases, web server) that are available to the primary container.

To make this work in a local devcontainer, you have to make sure that the devcontainer and the services are in the same network namespace. You can this by setting the `network_mode` of the devcontainer service to `service:<service-name>`, where `service-name` is the service you want to be available to your devcontainer. In addition, you can expose the port of the service to the host by setting the `forwardPorts` attribute of the devcontainer specification.

## tmp-mount
