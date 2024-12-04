
## run docker on server restart 

update running docker container 

`$ docker update --restart=always 84e3c304cdfd`

or on create container

`docker run -v jiraVolume:/var/atlassian/application-data/jira --restart=always --name="jira2" -d -p 8090:8080 atlassian/jira-software`

```
--restart=always not at last
```

