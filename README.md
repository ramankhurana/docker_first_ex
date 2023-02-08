This is the first example to demonstrate the docker usage: 
- create a package 
- create a docker image 
- Host image on repository 
- run image on target machine 

## Create the application 
Here I have created a very simple python script [main.py] which prints "This is first exmaple for docker image creation and deployment". Your application can be as simple as a print 
statement or very complex the steps remains almost the same. 

## Create the Dockerfile 
This file will have all the commands/instructions one need to follow in order to run the application. To run a python file one would need: 
1. python 
2. copy the file to the container 
3. run the file using python ./main.py 

This is what is being done in the three liner Dockerfile in this project. Again this file will change and evolve as the application becomes more complex and have more dependencies. 

## Build e docker image 
In order to create the docker image, enter the project directory and execute 
docker build -t docker_first_ex .


-t: allows you to decide the name of the image 
. : This is the path from where docker will collect all the files. A dot represents present directory. 


You will see docker processing the steps inside Dockerfile and output something like: 

Successfully built 42a9c1fe3101
Successfully tagged docker_first_ex:latest


## List the image 
docker image ls -a

REPOSITORY                           TAG         IMAGE ID       CREATED          SIZE
docker_first_ex                      latest      a2143aa55673   8 seconds ago    925MB



## Login to DockerHub web  
Create and account or sign in to dockerhub.com using your username and password. This will be used to check that the image os pushed to the dockerhub. 

## Login to commandline 
Login to dockerhub using commandline 

docker login 
username: 
password: 

## Change the tag of image 
docker tag docker_first_ex:latest docker_first_ex:0.0.0
left one is old image_name:tag, right is new image_name:tag

## Push to dockerhub 
Change the tag so that it has your username 
docker tag a2143aa55673 docker_user_name/docker-first-ex

docker push docker_user_name/docker-first-ex


## Look for image 
Now look for your image details and statistics on dockerhub.com page. 



