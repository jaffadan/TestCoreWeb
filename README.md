# TestCoreWeb
A sample containerized website using dotnetcore and docker.

build using

docker build -t testcoreweb .

-t => tag for image


run using 

docker run -d -p 2222:80 --name coresite testcoreweb

-d => detach our terminal

-p => port mapping (localport : containerport)

--name corresponds to a name we want to give to the container we're creating here.


check ports using 

docker port coresite


using the above command list, you'll then be able to navigate to the site at http://localhost:2222
