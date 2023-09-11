FROM adoptopenjdk/openjdk11

WORKDIR /usr/app/jira
ADD https://product-downloads.atlassian.com/software/jira/downloads/atlassian-jira-software-8.13.27.tar.gz jira.tar.gz
RUN mkdir home; tar -xvf jira.tar.gz -C . && rm -rf jira.tar.gz && sed -i 's#<Context path=""#<Context path="/jira"#' ./atlassian-jira-software-8.13.27-standalone/conf/server.xml
ENV JIRA_HOME=/usr/app/jira/home
EXPOSE 8080
ENTRYPOINT ["/usr/app/jira/atlassian-jira-software-8.13.27-standalone/bin/start-jira.sh", "-fg"]
