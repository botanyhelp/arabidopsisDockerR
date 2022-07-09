## docker is made of 3 things: server, client, api

### server, dockerd
    * long running daemon **dockerd**
    * creates and manages docker objects, including:
        * containers
        * images
        * networks
        * volumes
        * swarms
    * listens to requests sent to the docker socket that can be mapped to another port or socket unix://var/run/docker.soc
### client, docker
    * command line tool, **docker**, sends commands to the server via the API
    * docker <--> API <--> dockerd
    * client commands are singular and precise:
        * run
        * create
        * restart
    * ..but the API is doing lots of work, for example, the API, when hearing **docker run**, will:
        * create a container,
        * ..and then create an image if it does not exist,
        * ..start the container once the image is built,
        * ..and then attach the container if its required, attach your terminals stdio to running container using containers ID or name
### api, glue between server and client, allows us to:
    * create, run and control containers
    * build, manage, commit, pull and push images
    * read and monitor logs from containers,
    * build and manage networks
    * create and control data volumes of persistent storage
    * provision docker swarms and scale services
    * the api connects the server, the docker engine **dockerd** to the client, **docker**, or, because its a RESTful API, to any client that implements parts of the API
