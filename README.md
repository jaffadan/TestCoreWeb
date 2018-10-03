# TestCoreWeb
A sample containerized website using dotnetcore and docker.  the site is the default website created with an ASPNETCORE MVC application.  It is exposed over port 80 in the docker file.

build using:

docker build -t testcoreweb .

-t => tag for image (works like a name, you can reference the images this way)


run using 

docker run -d -p 2222:80 --name coresite testcoreweb

-d => detach our terminal

-p => port mapping (localport : containerport)  this will allow you to test that the site is running by port forwarding the localport to the container's port.  i exposed port 80 in my docker file, so the above command is port forwarding port 2222 on localhost to the container's port 80

--name corresponds to a name we want to give to the container we're creating here.


check ports using 

docker port coresite


using the above command list, you'll then be able to navigate to the site at http://localhost:2222


to stop the image after its running 

docker stop coresite


to list containers

docker container ls -a

to remove containers:

docker rm <container name/id>


to remove images 

docker rmi <image name>
  
  
