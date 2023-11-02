
FROM jenkins/agent:alpine-jdk11

USER root

# Install the required dependencies
# RUN apk --no-cache add \
#     curl \
#     ca-certificates

RUN apk add --no-cache \
	ca-certificates \
	curl \
	\
	# .NET Core dependencies
	krb5-libs \
	libgcc \
	libintl \
	libssl1.1 \
	libstdc++ \
	zlib \
	icu-libs \
	icu-data-full

# Install .NET Core 7 (or the version you've already installed)
# RUN apk --no-cache add dotnet-sdk7

# Download and install .NET Core 3.1 using dotnet-install.sh
RUN curl -SL --output dotnet-install.sh https://dot.net/v1/dotnet-install.sh \
	&& chmod +x dotnet-install.sh \
	&& ./dotnet-install.sh --version 3.1.412 --install-dir /usr/share/dotnet \
	&& rm dotnet-install.sh

# Add .NET Core 3.1 to PATH
ENV PATH="/usr/share/dotnet:$PATH"

# Verify .NET Core installations
RUN dotnet --version
RUN dotnet --list-sdks
