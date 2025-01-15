# dokku-dynamic-dockerfile

Plugin for dokku to dynamically build the base image from a Dockerfile.

## Installation

On your dokku server:

```sh
sudo dokku plugin:install https://github.com/SmBe19/dokku-dynamic-dockerfile dynamic-dockerfile
```

## Usage

This plugin can only be used with the herokuish builder.

Set the path to a folder in your project containing a Dockerfile:

```sh
dokku dynamic-dockerfile:set my_app dockerfile-path relative/path/to/context
```

The Dockerfile should provide the same functionality as the default base image. The easiest solution is to use "FROM gliderlabs/herokuish:latest-24" as a base for your Dockerfile.

When you deploy your project, the Dockerfile will be built and the resulting image will be used for the running the buildpacks and the subsequent deployment of your app.
