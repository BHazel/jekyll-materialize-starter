# Jekyll with MaterializeCSS Starter

This repository contains the source code for a [Jekyll](https://jekyllrb.com) site starter kit using [MaterializeCSS](https://materializecss.com) for the theme.  It includes in-built telemetry powered by [Azure Application Insights](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview).

## Usage

This kit is optimised to work with a development environment running in a Docker container.  To create the Docekr image run:

```bash
docker image build -t x-jekyll-starter -f dev.Dockerfile .
```

Run the following to start a container:

```bash
docker container run -it --rm -v /path/to/repo:/src -p 4000:4000 x-jekyll-starter bash
```

Once running a Jekyll server can be started from the _Makefile_:

```bash
make start
```

## Deployment

The site can be built for deployment from the _Makefile_.  The output is saved to the _dist_ directory:

```bash
make build
```

A Docker image of the site, based on NGINX, can be created from the _Dockerfile_:

```bash
docker image build -t x-site .
```