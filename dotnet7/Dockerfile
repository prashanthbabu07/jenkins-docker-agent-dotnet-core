# # Use the jenkins/agent:alpine-jdk11 as the base image
# FROM jenkins/agent:alpine-jdk11

# USER root

# # Install dependencies required for .NET Core
# RUN apk --no-cache add \
# 	curl \
# 	libc6-compat \
# 	libgcc \
# 	libstdc++ \
# 	musl-dev

# # Install the dynamic linker reqauired by .NET Core
# RUN ln -s /lib/libc.musl-x86_64.so.1 /lib/ld-linux-x86-64.so.2

# # Install .NET SDK 7.0
# RUN apk --no-cache add curl && \
# 	curl -SL --output dotnet.tar.gz https://dotnetcli.blob.core.windows.net/dotnet/Sdk/7.0.310/dotnet-sdk-7.0.310-linux-x64.tar.gz && \
# 	mkdir -p /usr/share/dotnet && \
# 	tar -zxf dotnet.tar.gz -C /usr/share/dotnet && \
# 	rm dotnet.tar.gz && \
# 	ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet

# # Set the .NET CLI user-wide installation
# ENV DOTNET_ROOT /usr/share/dotnet
# ENV PATH $PATH:/usr/share/dotnet

# # Optionally, set environment variables and configure additional tools if needed
# # ENV YOUR_ENV_VARIABLE=your_value

# # Optionally, install additional packages or tools

# # Switch to the Jenkins user
# USER jenkins

# # # # You can define any additional setup or configuration steps needed by your Jenkins agent

# # # bard

# # # FROM ubuntu:latest

# # # RUN apt update && apt install -y openjdk-11-jdk

# # # RUN dotnet tool install -g dotnet-jenkins-agent

# # # RUN dotnet tool install -g dotnet-sdk-7.0.0

# # # CMD ["dotnet-jenkins-agent"]


# # # # Use the official Ubuntu image as the base image
# # # FROM ubuntu:latest

# # # # Install dependencies and prepare for .NET Core installation
# # # RUN apt-get update && apt-get install -y \
# # #     openjdk-11-jre-headless \
# # #     wget \
# # #     && rm -rf /var/lib/apt/lists/*

# # # # Download and install Jenkins agent
# # # # You should replace "http://jenkins-server:port" with your actual Jenkins server URL
# # # RUN mkdir -p /usr/share/jenkins/agent
# # # WORKDIR /usr/share/jenkins/agent
# # # RUN wget http://localhost:8080/jnlpJars/agent.jar

# # # # Install .NET Core
# # # RUN wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
# # # RUN dpkg -i packages-microsoft-prod.deb
# # # RUN apt-get update && apt-get install -y dotnet-sdk-7.0
# # # RUN rm packages-microsoft-prod.deb

# # # # Optionally, install any other tools or dependencies you need for your build environment

# # # # Set up the entry point to start the Jenkins agent
# # # ENTRYPOINT ["java", "-jar", "/usr/share/jenkins/agent/agent.jar"]



# # Use the official Ubuntu image as the base image
# FROM ubuntu:latest

# # Install dependencies required for .NET Core and Jenkins agent
# RUN apt-get update && apt-get install -y \
#     openjdk-11-jdk \
#     curl \
#     && rm -rf /var/lib/apt/lists/*

# # Download and install Jenkins agent
# # Replace the URL with the actual Jenkins server URL
# RUN mkdir -p /usr/share/jenkins/agent
# WORKDIR /usr/share/jenkins/agent
# COPY agent.jar /usr/share/jenkins/agent/
# #RUN wget https://drive.google.com/u/0/uc?id=19SfiJEW2NiHAYJEXdK_i95ZWkFLsZggQ&export=download

# # Install .NET Core
# # Instructions for installing .NET Core can be found on the official .NET website
# # RUN curl -SL -o dotnet.tar.gz https://dotnetcli.blob.core.windows.net/dotnet/Sdk/7.0.310/dotnet-sdk-7.0.310-linux-x64.tar.gz
# COPY dotnet-sdk-7.0.310-linux-x64.tar.gz dotnet.tar.gz
# RUN mkdir -p /usr/share/dotnet
# RUN tar -zxf dotnet.tar.gz -C /usr/share/dotnet
# RUN rm dotnet.tar.gz

# # Add .NET to the system PATH
# ENV PATH="$PATH:/usr/share/dotnet"

# # Optionally, you can install any other tools or dependencies you need for your build environment

# # Set up the entry point to start the Jenkins agent
# ENTRYPOINT ["java", "-jar", "/usr/share/jenkins/agent/agent.jar"]





# Use the jenkins/agent:alpine-jdk11 image as the base image
FROM jenkins/agent:alpine-jdk11

USER root

# RUN wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
# RUN chmod +x ./dotnet-install.sh
# RUN ./dotnet-install.sh --channel 7.0

# Install dependencies required for .NET Core
RUN apk --no-cache add \
	curl 

RUN apk add dotnet7-sdk
	# zlib1g 

	# RUN apk update \
	#     && apk install -y --no-install-recommends \
	#         libc6 \
	#         libcurl3 \
	#         libgcc1 \
	#         libgssapi-krb5-2 \
	#         libicu57 \
	#         liblttng-ust0 \
	#         libssl1.0.2 \
	#         libstdc++6 \
	#         libunwind8 \
	#         libuuid1 \
	#         zlib1g \
	#     && rm -rf /var/lib/apt/lists/*

	# Download and install .NET Core 7
	# COPY dotnet-sdk-7.0.310-linux-x64.tar.gz dotnet.tar.gz
# RUN curl -SL -o dotnet.tar.gz https://download.visualstudio.microsoft.com/download/pr/eedac53d-79e5-4d8a-a33e-b1b0424f39c3/7e9dabe54e2d74f19bc39e7d42a1b1eb/dotnet-sdk-7.0.101-linux-musl-x64.tar.gz \
# RUN mkdir -p /usr/share/dotnet \
# 	&& tar -zxf dotnet.tar.gz -C /usr/share/dotnet \
# 	&& rm dotnet.tar.gz




# Add .NET to the system PATH
# ENV PATH="$PATH:/usr/share/dotnet"
# ENV DOTNET_ROOT /usr/share/dotnet
# ENV PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools

# Optionally, you can install any other tools or dependencies you need for your build environment

# Set up the entry point to start the Jenkins agent
# ENTRYPOINT ["java", "-jar", "/usr/share/jenkins/agent/agent.jar"]
