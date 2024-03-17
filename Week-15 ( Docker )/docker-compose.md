Here's a breakdown of your instructions and how to use Docker Compose for streamlining application management.

**Understanding Docker Compose**

* **Purpose:** Simplifies how you manage applications composed of multiple containers. This means less manual work to start, stop, and link your containers.
* **Mechanism:** Uses a `docker-compose.yml` file to define your services (like your MongoDB database and backend). You outline dependencies, network connections, port mappings, and volumes within this single file..
* **Core Advantage:** One command (`docker-compose up`) to launch all your containers and their configurations in concert.

**Instructions Breakdown**

**Before Docker Compose**

Your 'before' steps demonstrate setting up the components manually:

1. **Network:** `docker network create my_custom_network` creates a custom network for containers to communicate.
2. **Volume:**  `docker volume create volume_database` provides persistent storage for your database.
3. **Mongo Container:** `docker run ... mongo` launches the MongoDB container, attaching it to the network and volume.
4. **Backend Container:** `docker run ... backend` runs the backend connected to the same network.

**After Docker Compose**

Now let's streamline using Compose:

1. **Installation:** Follow the guide at [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/) to get Docker Compose on your system.

2. **YAML File (docker-compose.yml):** 

   ```yaml
   version: '3.8' # Specify a Compose file version

   services:
     mongo:
       image: mongo
       volumes: 
         - volume_database:/data/db
       networks:
         - my_custom_network

     backend:
       image: backend # Assuming you've built this image
       ports:
         - "3000:3000"
       networks:
         - my_custom_network

   networks:
     my_custom_network:

   volumes:
     volume_database:
   ```

3. **Launch:** `docker-compose up` will read this file and launch your containers according to the specifications.
4. **Shutdown:** `docker-compose down --volumes` tears down the containers and the associated volumes.

**Key Points**

* Compose files are customizable; add more services, environment variables, etc., as your application needs grow.
* The default behavior of Compose is to create a network for your services automatically, so often you don't need to define one explicitly.  
* `--volumes` is important when stopping containers if you want to destroy persistent data.
