FROM adoptopenjdk/openjdk11

WORKDIR /usr/app/jira
RUN mkdir home; tar -xvf jira.tar.gz -C . && rm -rf jira.tar.gz
ENV JIRA_HOME=/usr/app/jira/home
EXPOSE 8080
ENTRYPOINT ["/usr/app/jira/atlassian-jira-software-8.13.27-standalone/bin/start-jira.sh", "-fg"]
