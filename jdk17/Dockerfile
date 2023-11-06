FROM jenkins/agent:alpine-jdk17

USER root

# Install dependencies required for .NET Core
RUN apk --no-cache add \
	sshpass \
	curl 