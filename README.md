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

* Must not amend application structure
* Must be containerised
* Must be accessible locally via port 8080

## Considerations

* Should be able to start locally with one command
* Should be able to update application in real time when running locally
* Should not conflict with other projects that may be building at the same time
* Should consider different environments (i.e. local, build, deploy)
* Should consider container patterns (i.e. linked/sidecar containers)
* Should consider container security
* Should consider container efficiencies (i.e. image size, run time)

## Discussion points

These are points to think about and to discuss at the next interview stage.

* Secrets management (passwords, tokens, etc)
* Infrastructure to host application
* Infrastructure provisioning
