# Interview Test Container

    Please fork this repo or push to a different origin before updating.
    This test should take no more than two hours.
    Upon completion send an accessible repo link to your point of contact.

## Context

As part of being able to be cross-platform (Linux, OSX, etc) and provider-agnostic (AWS, GCP, etc), 
we require all of our applications to run within containers.
The same application should run in a near identical way whether it's from one developer machine to another,
or from one developer to our production environment.

Choose from either the Node application or PHP application provided and following the criteria/considerations below, 
containerise it.

## Criteria

- [x] Must not amend application structure
    - Application source files copied into container as-is
- [x] Must be containerised
    - Containerised with Docker
- [x] Must be accessible locally via port 8080
    - Port 8080 exposed inside the container and mapped to 8080 on the host

## Considerations

* Should be able to start locally with one command
    * `docker-compose up` or `docker run -p 8080:8080 stephenchinnadorai/interview-test-container`
* Should be able to update application in real time when running locally
    * Use `dev-interview-test-container` to mount local source files and update them in real time without the need to rebuild the container and copy files in.
    * Note that `nodemon` is needed for node to reflect changes in real time without a restart
* Should not conflict with other projects that may be building at the same time
    * Unique image name ensures that the image is distinguishable from and won't conflict with others
* Should consider different environments (i.e. local, build, deploy)
    * Image is built for production with packages installed with `npm ci` and source files `src/` baked into the image to ensure this artifact runs the same everywhere
    * For development/testing, a second docker-compose service with a volume mount to source files the host is provided, which uses the same image for production, but enables the source files to be updated on the fly. 
    
* Should consider container patterns (i.e. linked/sidecar containers)
* Should consider container security
    * `node:10.15.3` base image - latest LTS release
    * `node` user - not `root`
* Should consider container efficiencies (i.e. image size, run time)
    * `node:alpine` slim base image
    * 73.3MB image size
    * Running with Docker's built-in `init` process, as Node is not designed to be PID 1 (doesn't respond to `SIGTERM`/CTRL+C, etc.)
    * Add resource constraints, such as memory limits to the container to prevent OOM killing the host

## Discussion points

These are points to think about and to discuss at the next interview stage.

* Secrets management (passwords, tokens, etc)
* Infrastructure to host application
* Infrastructure provisioning
