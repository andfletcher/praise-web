# How to install Praise on Digital Ocean

The installation process requires only basic server knowledge and takes about 30 minutes. We have verified the installation on Digital Ocean but should with little or no modifications work on any Ubuntu server.

## Create a Droplet

When writing this guide we used the following Droplet config:

- Ubuntu 20.04 (LTS) x64
- 80 GB disk
- 4 GB memory

Praise might well run on a smaller setup as well, that is yet to be determined though.

## Configure a hostname

The webserver hosting the Praise dashboard automatically generates https certificates and therefore needs be configured with a hostname. Configure an `A RECORD` at your DNS provider that points to the Droplet IP.

For example, the Commons Stack Praise DNS setup:

| TYPE | DOMAIN NAME             | IP             | TTL    |
| ---- | ----------------------- | -------------- | ------ |
| A    | praise.commonsstack.org | 167.172.63.125 | 30 min |

## Use ssh to access Droplet

```
ssh root@xxx.xxx.xxx.xxx
```

This guide installs Praise under the root user, making no effort to secure the server. The following steps are optional but highly recommended:

- [Set up a firewall plus a user account with reduced privileges](digital-ocean-initial-setup.md)

## Install Docker

The Praise database runs on MongoDB, managed by Docker.

Complete step 1-2 of the installation guide: [How To Install and Use Docker on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

- Step 1 — Installing Docker
- Step 2 — Executing the Docker Command Without Sudo

:::info

If ou are using `ufw` as firewall, [additional configuration of Docker is needed](configure-ufw-for-docker.md).

:::

## Install Docker Compose

Docker compose is utility for configuring and running Docker containers. Praise requires `docker compose` v2 to be installed.

Complete step 1 in the installation guide: [How To Install and Use Docker Compose on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-22-04)

- Step 1 — Installing Docker Compose

## Pull Praise repository from GitHub

Clone the Praise repository from GitHub:

```
git clone https://github.com/CommonsBuild/praise.git
```

## Create a Discord bot

The Discord bot used to interact with Praise is created in the Discord developer dashboard. Take note of the various bot ids during bot creation as they will be used in the next step.

- [Create the Praise Discord bot](create-discord-bot.md)

## Configure environment

Run the Praise setup script to configure the runtime environment:

```
cd praise
bash setup.sh
```

## Start Praise

```
bash start.sh
```

## Finished 🎉

Your praise system should be up and running!
