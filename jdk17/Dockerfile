FROM jenkins/agent:alpine-jdk17

USER root

# Define the Maven version to install
ENV MAVEN_VERSION 3.9.4

# Define the download URL for the Apache Maven binary
ENV MAVEN_URL https://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz

# Download and install Apache Maven
RUN apk --no-cache add curl tar \
    && curl -fsSL -o /tmp/apache-maven.tar.gz $MAVEN_URL \
    && tar -xzf /tmp/apache-maven.tar.gz -C /opt \
    && ln -s /opt/apache-maven-$MAVEN_VERSION /opt/maven \
    && rm /tmp/apache-maven.tar.gz \
    && apk del curl tar

# Set the environment variables to include Maven in the PATH
ENV M2_HOME /opt/maven
ENV MAVEN_HOME /opt/maven
ENV PATH $M2_HOME/bin:$PATH

# Verify Maven installation
RUN mvn --version

# Install dependencies required for .NET Core
# RUN apk --no-cache add \
# 	sshpass \
# 	curl \
# 	maven

# RUN wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz
# RUN tar -xzf apache-maven-3.9.4-bin.tar.gz
# RUN mv apache-maven-3.9.4 /usr/local/bin

# RUN mvn --version