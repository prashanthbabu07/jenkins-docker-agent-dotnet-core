# Use the jenkins/agent:alpine-jdk11 image as the base image
FROM jenkins/agent:alpine-jdk11
USER root

# Install dependencies required for .NET Core
RUN apk --no-cache add \
	sshpass \
	curl 

RUN apk add dotnet7-sdk