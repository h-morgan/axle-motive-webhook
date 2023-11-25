# Axle Interview Project

This project is a backend webhook service that retrieves data from the [Motive API](https://developer.gomotive.com/reference/introduction), loads the data to blob storage, and notifies a callback URL of data loads.

The data we retrieve from the Motive API includes:

- vehicles
- drivers (from `/users` endpoint)
- trailers (from `/assets` endpoint)

## Overview

The project is deployed in AWS ECS, and data loads are stored in S3 blob storage. Data is also sent to the callback URL, with additional metadata about the load.

You'll notice there are 2 versions of the same service in this repo:

- Go version: [go-motive-webhook](https://github.com/h-morgan/axle-interview/tree/main/go-motive-webhook)
- Python version: [python-motive-webhook](https://github.com/h-morgan/axle-interview/tree/main/python-motive-webhook)

The reason for this is that Python is the language I'm most comfortable in, so I started by writing a first pass version in Python. For the purposes of the project, we're mainly interested in the Go version - this is the version currently running in AWS.

## How to run