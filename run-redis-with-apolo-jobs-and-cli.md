# Running Redis with Apolo Jobs and CLI

Learn how to configure and run Redis, an in-memory database, using Apolo cloud infrastructure and Apolo CLI.

## Prerequisites

This guide assumes that you are already authenticated with Apolo, have the Apolo CLI installed, and have access to a compute cluster and project.

This guide will walk you through the process of running Redis, an open-source, in-memory data store, using Apolo Jobs and CLI.

## Discovery

Redis is available as a publicly accessible container image on various container registries. You can locate the official Redis image on Docker Hub: https://hub.docker.com/_/redis

The latest version of the Redis image at the time of writing this guide is `redis:7.0.11`. Make a note of this version or any other version you prefer to use.

## Installation

Apolo Jobs play a crucial role in setting up and running Redis. Follow these steps to configure and launch a Redis job:

1. Create a new job using the Apolo CLI:

    ```bash
    apolo job create redis --image redis:7.0.11
    ```

