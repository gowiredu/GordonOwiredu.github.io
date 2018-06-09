# Planet Installation and Configuration

We are currently rewriting BeLL, the project is called **[`planet`](https://github.com/open-learning-exchange/planet)**. The objective is to create a Progressive Web App using Angular & CouchDB with the BeLL Apps functionality.

Please follow the directions below to install your community `planet` and its dependencies to your machine.

## Install Docker

In order to run `planet`, you will need Docker Community Edition installed.

### Windows

[Chocolatey](https://chocolatey.org/) – the package manager for Windows was installed to your machine in the previous step.

If you have 64bit Windows 10 Pro, Enterprise and Education (1607 Anniversary Update, Build 14393 or later), please follow the official [Install Docker for Windows](https://docs.docker.com/docker-for-windows/install/) guide or run `choco install docker-for-windows`.

Otherwise you will need to ...

### macOS

If you are running macOS El Capitan 10.11 and newer macOS releases, please follow the official [Install Docker for Mac](https://docs.docker.com/docker-for-mac/install/) guide.

### Linux

Please find your distro at https://docs.docker.com/install/#server and follow the guide.

## Planet Installation

1. Launch Docker on your machine

1. Go to your OLE project folder

1. Clone the `planet` repository: `git clone https://github.com/open-learning-exchange/docker.git`

1. Go to 'planet/docker' folder: `cd planet/docker`

1. Run the following command to spawn your environment for the **first time**: `docker-compose -f planet.yml -p planet up -d --build`

1. See if the docker containers are running: `docker ps`. You'll see your running container similar to this

  ```
  CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS              PORTS                                                                NAMES
  ea3b914c3193        planetdev_planet    "/bin/sh -c 'bash ..."   About a minute ago   Up 58 seconds       0.0.0.0:3000->3000/tcp                                               planetdev_planet_1
  57f30698ccda        klaemo/couchdb      "tini -- /docker-e..."   About a minute ago   Up About a minute   4369/tcp, 9100/tcp, 0.0.0.0:2200->5984/tcp, 0.0.0.0:2201->5986/tcp   planetdev_couchdb_1
  ```

1. See log in action with `docker-compose -f planet.yml -p planet logs -f`, press 'CTRL+C' to exit logs view

## Planet Configuration

Go to your community `planet` at <http://localhost:3000>. You will be asked to:

- Create an admin account
- Fill out configuration
  - To cerate your `planet` community and connect to the Virtual Intern Nation:
    - Select `Community` from `Select Nation/Community`drop-down
    - Select `vi` from `Nation(s)` drop-down
    - Use your GitHub username as `Name`
    - Use upper case of your GitHub username as `Code` (so we can easily identify your community in Virtual Intern Nation)
- Fill out contact details
- Click `Submit` and let us know in the Gitter chat.

![Planet Community Configuration](images/vi-planet-configuration.png)

After logging in, please explore around and post a screenshot of your `planet` to the Gitter chat.

![Planet UI Screenshot](images/vi-planet-ui-screenshot.png)

When you're done, you can stop `planet`: `docker-compose -f planet.yml -p planet stop`
When you want to have `planet` up and running again: `docker-compose -f planet.yml -p planet start`

## Useful Links

[FAQ – Helpful links](vi-faq.md#Helpful_Links)

## Next Section

Now you have `panet` installed, head over to [Docker Tutorial](vi-docker-tutorial.md) to learn about the basics of interacting with Docker and Docker Compose through the command-line interface.

#### Return to [First Steps](vi-first-steps.md#Step_2_-_Planet_and_Docker)