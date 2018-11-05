# Emoji Search
---

This is react app searches for emoji. This project autodeploy emoji-search react app on every commit in git-hub on docker container located on azure cloud. [Jenkins](https://jenkins.io/) ci job build is called on every commit in github.

## Installation
### Checkout Repository
```
$git clone https://github.com/dgawade1407/emoji-search.git
```
### 1. Deploy inside Docker
---
##### Pre-Requisite:
* Docker should be installed on your machine. Refer [Install Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04) documentation.

##### Steps to start  CI server
Find [Dockerfile jenkins](https://github.com/dgawade1407/emoji-search/blob/master/jenkins-docker/Dockerfile) in repository under jenkins-docker directory.
cd to emoji-search repo and run following command.
```
sudo docker build -t prujenkins:latest jenkins-docker/.

sudo docker run -p 9090:8080 -v /var/run/docker.sock:/var/run/docker.sock  --name ci-jenkins -d prujenkins
```

after above step acces ci server.
```
http://<yourip>:9090/job/oncommit_ci/
e.g  http://40.76.4.149:9090/job/oncommit_ci/
```
configure job for get latest from github and deploying it on node.(Refer jenkins.io)
[Jenkins file](https://github.com/dgawade1407/emoji-search/blob/master/Jenkinsfile) for refernce

##### Steps to start  App server
Find [Dockerfile](https://github.com/dgawade1407/emoji-search/blob/master/Dockerfile) in repository.
cd to emoji-search repo and run following command.
```
sudo docker build -t pruci/emojisearch-dev:latest .
sudo docker run -p 3000:3000 --name app-server -d emojisearch-dev
```

after above step acces app server.
```
http://<your-ip>:3000/
e.g  http://40.76.4.149:3000/
```
commit changes git-hub repository and access app server to see new changes




