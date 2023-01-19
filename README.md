Installing jenkins and CI/CD TASK

Open aws and lauch linux server

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


open terminal![Screenshot (346)](https://user-images.githubusercontent.com/119240540/212384293-4f6ce40b-32c9-407f-8149-9ac1e3a0908d.png)


open vi docker-compose.yml

version: '3.9'

services:

  jenkins:
  
    image: jenkins/jenkins:lts
    
    container_name: jenkins_demo
    
    restart: always
    
    ports:
    
    - "8080:8080"


![Screenshot (347)](https://user-images.githubusercontent.com/119240540/212384327-3e6a54fd-2975-452a-8457-282da8658525.png)
open jenkins portal 


copy path and 
in vm sudo docker exec -it <dockerimage> bash

![Screenshot (348)](https://user-images.githubusercontent.com/119240540/212384353-6a89e6cf-c2d4-4de7-b751-121a40ffc002.png)
create project
![Screenshot (349)](https://user-images.githubusercontent.com/119240540/212384384-c315273d-7acc-4b69-a00c-93b012aad103.png)

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


![Screenshot (351)](https://user-images.githubusercontent.com/119240540/212384437-fd1e48ca-df30-48f0-89ed-51e43316639a.png)
![Screenshot (350)](https://user-images.githubusercontent.com/119240540/212384409-f7830477-3cbb-4827-a455-d6526c86e04f.png)
![Screenshot (352)](https://user-images.githubusercontent.com/119240540/212384465-aa1e3170-a249-49f1-9e65-117e9677047b.png)
![Screenshot (353)](https://user-images.githubusercontent.com/119240540/212384480-92009460-3d39-4795-b0ca-9ac9e48fdf3d.png)
![Screenshot (354)](https://user-images.githubusercontent.com/119240540/212384496-86498ece-9b5b-468f-8ae0-3d66c3a483cb.png)
![Screenshot (355)](https://user-images.githubusercontent.com/119240540/212384510-198dd309-d46a-44ce-874f-a5a0356d0ad7.png)
![Screenshot (356)](https://user-images.githubusercontent.com/119240540/212384526-d8519add-524a-457c-a919-4e723be71fb1.png)
![Screenshot (357)](https://user-images.githubusercontent.com/119240540/212384541-26d7984d-613e-4c0a-a473-8fb57c7bc229.png)

and performe these commands


 
    


