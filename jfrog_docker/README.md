# Setup

​
Create Docker volumes.

    docker volume create --name=artifactory_data
    docker volume create --name=postgres_data

Extract the contents of the compressed archive and go to the extracted folder.

    tar -xvf jfrog-artifactory-<pro|oss|cpp-ce>-<version>-compose.tar.gz
    cp templates/docker-compose-volumes.yaml docker-compose.yaml

Add the entries in the .env file.
Avoid adding duplicate entries in the

    echo -e "JF_SHARED_NODE_IP=$(hostname -i)" >> .env
    echo -e "JF_SHARED_NODE_ID=$(hostname -s)" >> .env
    echo -e "JF_SHARED_NODE_NAME=$(hostname -s)" >> .env

Manage Artifactory using native Docker Compose commands:

    docker-compose -p rt <action> command

Run these commands from the extracted folder.

    docker-compose -p rt up -d
    docker-compose -p rt ps
    docker-compose -p rt down
