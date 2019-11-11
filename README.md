# `docker-compose` config for Documize

## Why?

Documize is a self-hosted alternative to Atlassian's Confluence.
It's a lightweight Go binary that serves a Wiki-like platform for sharing information
across teams.

## First Run

1. Download the latest `linux-amd64` binary from here: https://github.com/documize/community/releases
2. Move the binary into `bin/`
3. Edit `bin/init.sh` so that it runs the `linux-amd64` binary. It should look like this:

	```bash
	# 'sleep 15' to wait for the PostgreSQL server to start up.
	# '/root/bin' is where we're mounting the 'bin/' folder on the 'documize' container
	sleep 15 && \
	/root/bin/documize-community-linux-amd64
	```

## Run the stack

```bash
docker-compose up --abort-on-container-exit
```