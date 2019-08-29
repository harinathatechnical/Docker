# Docker


Image contains has -> FS Snapshot + Start up Command 

Docker ps -> see all the processes running 

Docker ps -- all  with all process run upto now 

Docker system prune  delete all stopped containers 

Docker start –a <<container id >>  a used to print the logs 

Docker logs <<contanersid>>  print the logs after started to need to see 

Docker exec –it <<contenerid>> <<command >>  execute command already running container 

Docker run <<imageName>> 
Or 
Docker create <<immagename>>
Docker start <<containeridwhich is coming from above >>

# Create docker image  With following 
   
    use an exising image as base 
      FROM alpine
    download and install a dependency 
      RUN apk add --update redis
    tell the imahe what to do when it start as acontainer
       CMD ["redis-server"}

    Then run in terminal as 
     Docker build .
     Successfully built 7aaa45ecd078 
     Then 
     Docker run << processID>>
     Docker run 7aaa45ecd078

# In details :- 
    FROM used for base image 
    RUN used to execute some command while prepare our custom image
    CMD used to what should be executing 
 
    Docker build :-  docker build . 

    COPY ./ ./ 
     Used to copy the files to container to run install sample is package.json like so 

    Container port mapping 
     Docker run –p <<local network port>>:<<Docker port>> <<Image_Name>>
     Docker run –p 8080:8080 hari/simpleweb
  
# Run Different name docker file as 
    Docker build –f <<docker_file_name>> .
     Successfully built 1040a59be6cc 
       it gives process id like above by using that run the docker 
    docker run 1040a59be6cc
   
     expose the post from docker image use 
    docker run -p 3000:3000 1040a59be6cc
  
    Docker Volume 
    docker run -p 3000:3000 -v $(pwd):/app  1040a59be6cc
  
  
   


