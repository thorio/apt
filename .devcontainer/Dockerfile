FROM debian:bookworm

RUN apt-get update && \
	apt-get install reprepro -y --no-install-recommends && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

RUN useradd user -m -s /bin/bash

USER user
