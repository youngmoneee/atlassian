FROM adoptopenjdk/openjdk11

WORKDIR /usr/app/bitbucket
ADD https://product-downloads.atlassian.com/software/stash/downloads/atlassian-bitbucket-7.21.15.tar.gz ./bitbucket.tar.gz
RUN mkdir -p home/shared; apt-get update -y && apt-get install git -y && tar -xvf bitbucket.tar.gz -C . && rm -rf bitbucket.tar.gz
RUN echo "" >> /usr/app/bitbucket/home/shared/bitbucket.properties && echo "server.context-path=/bitbucket" >> /usr/app/bitbucket/home/shared/bitbucket.properties
ENV BITBUCKET_HOME=/usr/app/bitbucket/home
EXPOSE 7990
ENTRYPOINT ["/usr/app/bitbucket/atlassian-bitbucket-7.21.15/bin/start-bitbucket.sh", "-fg"]
