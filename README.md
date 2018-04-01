# GitLab Runner for Kontena environment

Kontena Stack for running GitLab Runner.

### Usage
Get the GitLab registration token from the repository:

    YOUR_REPOSITORY -> Settings -> CI/CD -> Runner settings

Install gitlab-runner-stack:

    $ kontena stack install

Enter the appropriate settings for the runner configuration for example:

    Enter the number of Runner instances? : 1
    Enter the gitlab-ci coordinator URL (e.g. https://gitlab.com) : https://gitlab.com
    Enter the gitlab-ci token for this runner : xxx
    Enter the gitlab-ci description for this runner : Kontena-Runner-in-local-grid
    Enter the gitlab-ci tags for this runner (comma separated e.g. first-tag,second-tag) : Kontena-Runner-in-local-grid
    Enter the executor - ssh, docker+machine, docker-ssh+machine, kubernetes, docker, parallels, virtualbox, docker-ssh, shell : docker
    Enter the Docker image (e.g. ruby:2.1) : alpine:latest
    Select private Docker image-registry pull policy : (Use arrow or number (1-3) keys, press Enter to select)
    1: always
    2: never
    3: if-not-present

Ensure that the runner(s) is/are activated for the project:

    YOUR_REPOSITORY -> Settings -> CI/CD -> Runner settings -> Runners activated for this project

### Scaling
Check the name of the Runner service:

    $ kontena service ls

Scale the service: 

    $ kontena service scale SERVICE_NAME desired-number-of-services
