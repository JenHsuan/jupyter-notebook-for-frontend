# Jupyter Notebook for Frontend developers
This docker file wraps a Jupyter Notebook with the following cores.
* JavaScript
* TypeScript
* Deno

It's created for frontend developers who want to learn or practice JavaScript, TypeScript, and Deno.

## Installation
1. Install Docker and the compose plugin
2. Build the docker image
```bash
# Execute the following command 
docker build -t jupyter -f ./docker/images/Dockerfile ./

# Or use the following npm command 
npm run dokcer-build
```

3. Create the docker container
```bash
# Execute the following command 
docker-compose --file ./docker/compose/docker-compose.yml up -d

# Or use the following npm command 
npm run docker-up
```

4. Open the browser and navigate to http://localhost:8888
  * The password for the Jupyter notebook is admin
5. Destroy the docker container
```bash
# Execute the following command 
docker-compose --file ./docker/compose/docker-compose.yml down

# Or use the following npm command 
npm run docker-down
```

## Details
* [Docker Container for Jupyter Notebook with Built-in Node.js, TypeScript, and Deno Cores](https://medium.com/a-layman/docker-container-for-jupyter-notebook-with-built-in-node-js-typescript-and-deno-cores-7106dc89c704)