# It Works In My Devcontainer

Devcontainers are (supposedly) standardized, reproducible development environments that can be shared with others. This repository is a collection of devcontainer configurations that behave differently when running them locally vs. running them in GitHub Codespaces.

1. [dockerComposeFile](#dockercomposefile)
2. [tmp-mount](#tmp-mount)

## dockerComposeFile

The `dockerComposeFile` attribute of the devcontainer specification allows you to specify one or more Docker Compose files to use when starting the devcontainer. This is useful for defining multi-container development environments, with one container being the primary development environment and the other containers being services (e.g. databases, web server) that are available to the primary container.



## tmp-mount