The easiest way to build and run this application is to use `docker-compose`. This is included with Docker on Mac and Windows. Follow [Docker's installation guide](https://docs.docker.com/compose/install/) for Linux or other platforms.

## Building
From this directory, run `docker-compose build`

This will build the `stephenchinnadorai/interview-test-container` Docker image and tag it.

## Running
To start up your newly built image and run it as a container
### Development
This container will mount your local source files so that you can make changes in real time.

```docker-compose up dev-interview-test-container```
### Production
This container will use the source files copied in at build time and sets the Node environment to production.

```docker-compose up interview-test-container```


Logs will appear in stdout and let you know that your app is up and running

```
$ docker-compose up
Recreating node_interview-test-container_1 ... done
Attaching to node_interview-test-container_1
interview-test-container_1  |
interview-test-container_1  | > interview-test-container@1.0.0 start /usr/src/app
interview-test-container_1  | > node ./src/app.js
interview-test-container_1  |
interview-test-container_1  | Example app listening on port 8080!
```

Navigate to http://localhost:8080 to see your Node app in action.

## Deploying
To push the application to a Docker registry, modify the `image:` name and point it to your private Docker Registry and add a version tag if necessary. Then, run `docker-compose push`.
