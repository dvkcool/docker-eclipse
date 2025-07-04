# docker-eclipse

Eclipse IDE for Enterprise Java and Web Developers (includes Incubating components) in a docker container

Version: 2025-06 (4.36.0)
Build id: 20250605-1316

## Requirements

* x11Docker
* Docker version 28.1.1+1

## Quickstart

Once you close Eclipse the container will be removed and no traces of it will be
kept on your machine (apart from the Docker image of course).
```sh
mkdir -p .eclipse-docker
x11docker \
  --home \
  --share="$(pwd)" \
  --clipboard \
  --network="my_custom_network" \
  --  \
  dvkcool/eclipse
```

### Making plugins persist between sessions

Eclipse plugins are kept on `$HOME/.eclipse` inside the container, so if you
want to keep them around after you close it, you'll need to share it with your
host.

For example:

```sh
mkdir -p .eclipse-docker
x11docker \
  --home \
  --share="$(pwd)" \
  --clipboard \
  --network="my_custom_network" \
  --  \
  dvkcool/eclipse
```

## Help! I started the container but I don't see the Eclipse screen

You might have an issue with the X11 socket permissions since the default user
used by the base image has an user and group ids set to `1000`, in that case
you can run either create your own base image with the appropriate ids or run
`xhost +` on your machine and try again.

##  Tested environment
1. OS: Linux Mint 22.1 Cinnamon
1. Cinamon version: 6.4.6
1. Docker version: 28.1.1+1
1. x11Docker version: 7.6.0


## Fork credits
Kudos to [fgrehm](https://github.com/fgrehm) for creating the base inspirtation

## Inspiration to make this work
My system used to crash when running the projects, so I wanted something that will prevent complete system crash.
Mainly to limit memory and CPU usage. Although you could say that I just wanted an excuse to brush up my x11 docker skill.

________________________________________________
Happy Coding

__________________________________________________
Divyanshu 
Team Spark
