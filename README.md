# Container Manager Script

A bash script I wrote to simplify managing my containers. Works with the following directory structure. 

```bash
$ tree -L 2  /path/to/my_containers/
.
├── containers
├── first
│   ├── config
│   └── docker-compose.yml
├── second
│   ├── config
│   └── docker-compose.yml.off
├── third
│   ├── data
│   └── docker-compose.yml
└── fourth
    └── docker-compose.yaml
```
## Get the Script 

Run the following in your container folder.

```
$ wget "https://raw.githubusercontent.com/nick-robo/container_manager_script/master/containers"
```

## Usage

Run `./containers help` for help.

```
Usage:  ./containers [command] CONTAINER_FOLDER
   or:  ./containers [command]              (acts on all containers which are on)

Available Commands:
    help        Print this command
    list        List all container folders by their state (on/off)
    update      Update and run container
    stop        Stop a running container
    start       Start a stopped container
    restart     Restart a running container
    on          Change state to on 
    off         Change state to off (will not be affected by other commands)
```
List containers by state.

```bash
$ ./containers list
ON
    first
    third
    fourth
OFF
    second
```

Start a container: `./containers start first`

Start all containers which are not off: `./containers start`

Off state prevents commands from working on the container.
