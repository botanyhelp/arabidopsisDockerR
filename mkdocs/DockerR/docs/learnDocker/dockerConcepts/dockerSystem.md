## docker system is lots of things:

### container
    * houses all libraries and dependencies required to run in isolation
    * isolates is contents from its surroundings, allowing us to manage container on multiple platforms
    * shares host OS kernel, allowing it to start instantly and use less RAM
### hub
    * cloud based registry service
    * hosts code repos, workflows, pipelines, collaboration tools
    * search for and download docker images from ubuntu, apache, mysql, etc
    * can push and pull our own images
    * both **docker cloud** and **docker hub** require **docker id**, a docker hub account
    * collaboration means:
        * teams of users
        * automated builds with webhooks can be used within the build pipeline
### compose
    * defines and runs multi-container apps
    * configure multiple services which make up your application in one or more **docker compose files**
    * **docker compose files** are YAML
    * useful when deploying to different sets of environments, dev, prod, etc
    * we will use compose to manage and deploy projects to our local environment
### image
    * compiled **dockerfile** whicn can be built into many container instances
    * a set of layers that create instances of immutable and isolated containers
### log
    * retrieve a containers log file at time of execution
    * accessed via **compose** and through **docker** cli
    * standard unix STDOUT and STDERR can be accessed via **docker log**
    * more steps may be required to access the container logs:
        * a service may send log output to a file or database instead of a stream..these will be unavailable until logging output is configured
        * different logging drivers can be supplied to alter how logs are handled, thus allowing docker to access the logs
### network
    * by default, docker will create a network between running containers
    * network behaves as a bridge between host and containers
    * new containers are automatically connected to this default bridge when run
    * the default bridge supports port mapping to allow communication between containers
    * we can supply different options when creating containers that allow us to use user-defined networks instead
    * these user-defined networks can be configure to behave like bridge networks, overlay networks, or MAC VLANs
### volume
    * data volumes for persistent or shared data
    * means for sharing and storing persistent data
    * a **host directory** can be **bind mounted** or a **docker volume** can be used
    * volumes can be shard amongst containers
    * backup and copy features are available
### swarm
    * a cluster of docker engines configured on remote docker machines
    * allows to manage multiple docker engines and therefore control multiple services that have been deployed
    * replication, load balancing, rolling image and configuration updates, multi-host networking, cluster management are possible with swarm
### registry
    * app for storing and distributing images
    * search, commit, push pull
### machine
    * virtual host setup to run docker engine
    * like a VM with its own docker engine and therefore its own set of containers
