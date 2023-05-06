# Jenkins Docker agent

- Sample Gihub project to test Jenkins Docker agent

## Prerequisites

- Docker plugin installed in Jenkins

- Docker Pipeline plugin installed in Jenkins

- Jenkins Setup in docker

```bash
docker run --name jenkins -w /var/jenkins_home -id -v jenkins:/var/jenkins_home --network host -p 80:8080 -p 50000:50000 -v $(which docker):/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock --restart unless-stopped jenkins/jenkins:lts
```


- Sample Github project to test Jenkins Docker agent

- Sample project 1
```github
https://www.jenkins.io/doc/book/pipeline/docker/
```

- Sample project 2
```github
https://github.com/jenkins-docs/simple-node-js-react-npm-app
```

- Sample project 3
```github
https://github.com/twuni/jenkins-nodejs-example/blob/master/Jenkinsfile
```






- Jenkins Dynamic Slaves (Host Network Required)

- Step1
 vim /lib/systemd/system/docker.service
 
 - Step2
- You can replace with below line:

```bash
ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:8443 -H unix:///var/run/docker.sock
```

- Step3
```bash
systemctl daemon-reload
systemctl restart docker
systemctl status docker
```

- Test
```bash
curl http://172.31.31.86:8443/version
 ```

 ```docker
docker run --name jenkins -w /var/jenkins_home -id -v jenkins:/var/jenkins_home --network host -v $(which docker):/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock --restart unless-stopped jenkins/jenkins:lts
```


docker restart jenkins

###############################################################
# https://www.youtube.com/watch?v=ymI02j-hqpU&feature=youtu.be
# https://github.com/darinpope/jenkins-example-docker
################################################################

###########################
# Sample Projects/Pipelines
###########################
# https://www.jenkins.io/doc/book/pipeline/docker/
# https://github.com/jenkins-docs/simple-node-js-react-npm-app
# https://github.com/twuni/jenkins-nodejs-example/blob/master/Jenkinsfile

# Note: Do not use ubuntu22 lts