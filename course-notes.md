# Course Notes
    
    docker build <path do Dockerfile> # builds a docker image
        -t <container name>:<container tag> # defines container name and tag

    docker ps # show all running containers
        -a # show all containers including stopped

    docker run <container name or hash> # run a container
        -p <local port:container port> <container name or hash> # run with published port
        -d <container name or hash> # run deatached
        -it <container name or hash> # run interactive mode with allocated tty
        -p <local port:container port> -d --rm <container name or hash> # run a container with published port, deatached and remove if it is stopped
        --name <container new name> # define a container custom name
        --rm # removes the container when stopped
        -v <volume name/host volume path:container volume path> # bind a host path to container path (-v $(pwd):/app can be used)
            add :ro to make sure a volume is read-only
        -e or --env <variable=value> # used to set environment variables
        --env-file <environment file name> # reads environment variables from and environment variables file
        --build-arg <variable=value> # send a value argument for building an image

    docker logs <local port:container port> # show container logs
        -f <local port:container port> # show container logs and stay attached

    docker start <container name or hash> # starts a container
        -a <container name or hash> # starts in attached mode
        -a -i <container name or hash> # starts in attached and interactive modes

    docker stop <container name or hash> # stops the container

    docker rm <container name or hash> # remove specified container

    docker images # list images

    docker rmi <image name or hash> # remove image

    docker image inspect <image name or hash> # inspects the container showing its infomation in json mode

    docker cp # copy files/folders from/to container 
        <path for folder or file> <container name or hash>:<path inside the container> # copy to container
        <container name or hash>:<path inside the container> <path for folder or file> # copy from container

    docker container prune # remove all stopped containers

    docker image prune # remove all dangling images (untagged ones)
        -a # remove them all

    docker volume # integract between container and host file systems
        create # create a new volume
        inspect # show information about volume
        ls # list existing volumes
        prune # remove unnamed volumes
        rm <volume name> # removes a volume by its name

    .dockerignore # is the file that contains diretories or files that will not be copied to te container

