# Running Redis with Apolo Jobs and CLI

## Overview

This guide walks you through the process of running Redis with Apolo Jobs and CLI. Redis is an open-source, in-memory data store commonly used as a database and cache. The guide covers the following aspects:

- [Discovery:](#discovery) Locating a publicly available container image, identifying its version, and recording essential details.
- [Installation:](#installation) Setting up Redis using Apolo Jobs, including necessary configuration steps and Apolo CLI commands.
- [Usage:](#usage) Verifying that a Redis job is operational and accessing the database through other jobs or Apolo CLI using port-forwarding.
- [Cleanup:](#clenup) Restoring the system to its original state.
- [Persistance configuration:](#configuring-redis-with-apolo-files-for-persistence) Configuring Redis with Apolo files for persistence.


## Prerequisites

Before you begin, ensure you have the following:

- Authenticated with Apolo
- Apolo CLI installed
- Access to a compute cluster and project

## Discovery

To locate a publicly available Redis container image:

1. Visit [Docker Hub](https://hub.docker.com/).
2. Search for "Redis".
3. Identify the official Redis image and note its version (e.g., `redis:6.2`).

## Installation

1. Create a Redis job using the Apolo CLI:

```sh
apolo run --name redis-job --preset cpu-small --volume storage:redis-data:/data:rw redis:6.2 --port 6379
```

1. Check the status of the Redis job:

```sh
apolo ps
```

Ensure the job is running and note the job ID.

## Usage

1. To access the Redis database from your local machine, use port-forwarding:

```sh
apolo port-forward <job-id> 6379:6379
```

1. You can now access the Redis database using a Redis client:

```sh
redis-cli -h localhost -p 6379
```

1. To access Redis from another job, create a new job and connect to the Redis job using the internal hostname:

```sh
apolo run --name redis-client --preset cpu-small --volume storage:redis-data:/data:rw redis:6.2 redis-cli -h redis-job -p 6379
```

## Clenup

To restore the system to its original state:

1. Terminate the Redis job:

```sh
apolo rm storage:redis-data
```

1. Remove the Redis data volume:

```sh
apolo rm storage:redis-data
```

## Configuring Redis with Apolo files for persistence

To configure Redis to use Apolo Files for persistence:

1. Create a volume for Redis data:

```sh
apolo mkvol storage:redis-data
```

1. Run the Redis job with the volume mounted:

```sh
apolo run --name redis-job --preset cpu-small --volume storage:redis-data:/data:rw redis:6.2 --port 6379
```