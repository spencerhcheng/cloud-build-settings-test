
The following is sample text:

    Start Ubuntu virtual machine using Vagrant (required to run docker):

    vagrant up

    SSH into virtual machine:

    vagrant ssh

    Install dependencies:

    cd /vagrant
    make install

    Build docker image:

    make build
    # docker build -t gasi/centos-node-hello .

    Run app:

    make run-container
    # docker run -p 49160:8080 -d gasi/centos-node-hello

    Install curl:

    sudo apt-get install curl

    Get mapped port (last column) using, e.g. 49160:

    docker ps

    > # Example
    > ID                  IMAGE                           COMMAND              CREATED             STATUS              PORTS
    > ecce33b30ebf        gasi/centos-node-hello:latest   node /src/index.js   10 seconds ago      Up 9 seconds        49160->8080

    Test app using the port in previous step, e.g. 49160:

    curl localhost:<port>

    # Example
    # curl localhost:49163

    It should print Hello World to the console.

    If you use Boot2Docker on OS X, the port is actually mapped to the Docker host VM, and you should use the following command:

    curl $(boot2docker ip):<port>

