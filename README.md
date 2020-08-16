# jenkins-docker-slave

## Pre-Requisites:
    - Install Git
    - Isntall Java
    - Install Docker
    - Install Jenkins
## Install Git:
    yum install git -y
## Install Java
    yum install java -y
## Install Jenkins
    sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
    sudo yum install jenkins -y
    service jenkins start
## Install Docker
    yum install docker -y
    usermod -aG docker jenkins
    service docker start
## Reastart Jenkins
    service jenkins restart
## Create Jenkins-slave Image
  Clone code from github
  
      git clone https://github.com/cloudtechmasters/jenkins-docker-slave.git
      cd jenkins-docker-slave
      docker build -t cloudtechmasters/jenkins-slave .
 Push Jenkins-slave Image to docker hub
       
       docker login
       docker push cloudtechmasters/jenkins-slave:latest
 ## Goto Jenins and Install below plugins
       - docker
       - docker pipeline
 ## Integrate docker image as slave in jenkins
 Goto Jenkins -->  Manage Jenkins --> configure system --> Cloud
 Click on a separate configuration page and click on docker
 ![image](https://user-images.githubusercontent.com/68885738/90334622-a020c700-dfec-11ea-882c-d9745ab499f5.png)
![image](https://user-images.githubusercontent.com/68885738/90334632-b4fd5a80-dfec-11ea-9e1f-a50965aa9aa4.png)
![image](https://user-images.githubusercontent.com/68885738/90334646-cb0b1b00-dfec-11ea-9aaa-87d739ec3dee.png)
![image](https://user-images.githubusercontent.com/68885738/90334654-deb68180-dfec-11ea-9018-8f23040ec942.png)
 
 Fill details as show above images and click on Save
 
 ## Create new jenkins pipeline job by click on New Item
 Paste content of Jenkins file with pipeline section
 ## Click on Build now
