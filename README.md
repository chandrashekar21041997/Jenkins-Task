Installing jenkins and CI/CD TASK

Open aws and lauch linux server

open terminal
and performe these commands

sudo yum update -y

### Installing Docker ###
sudo yum install docker -y
sudo systemctl start docker
sudo systemctl enable docker

### Installing docker-compose ###
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
### Installing Git ###
sudo yum install git -y
 
 after instalation
 
open vi docker-compose.yml
version: '3.9'
services:
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins_demo
    restart: always
    ports:
    - "8080:8080"
    
close

sudo docker-compose up -d
sudo docker ps
sudo docker exec -it <imagename> bash
cat Jenkinslink

copy and paste into jenkins server

jenkins install pre-requests

create a free style project
add git link

mkdir guvi
ls
cp Dockerfile guvi/
cp index.html guvi/
tar -cvf guvi.tar.gz guvi/
scp -T -o StrictHostkeyChecking=no -i $key guvi.tar.gz ec2-user@13.115.130.16:/home/ec2-user/
ssh -T -o StrictHostkeyChecking=no -i $key ec2-user@13.115.130.16 << EOF
cd /home/ec2-user/
ls
tar -xvf guvi.tar.gz
cd guvi/
ls
sudo docker build -t demo:v1 .
sudo docker images
sudo docker run -it -d -p 80:80 --name test demo:v1
sudo docker ps

FROM ubuntu
RUN apt update -y && \
    apt install nginx -y
COPY index.html var/www/html
CMD ["nginx", "-g", "daemon off;"]
