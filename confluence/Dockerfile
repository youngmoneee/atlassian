FROM adoptopenjdk/openjdk11

WORKDIR /usr/app/confluence
ADD https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-8.5.1.tar.gz ./confluence.tar.gz
RUN mkdir home; tar -xvf confluence.tar.gz -C . && rm -rf confluence.tar.gz && echo "confluence.home=/usr/app/confluence/home" > /usr/app/confluence/atlassian-confluence-8.5.1/confluence/WEB-INF/classes/confluence-init.properties
EXPOSE 8090 8091
ENTRYPOINT ["/usr/app/confluence/atlassian-confluence-8.5.1/bin/start-confluence.sh", "-fg"]
