# Docker

![Docker1](images/Docker1.png?raw=true "Title")

## Why use Docker?

* Makes life really easy for installing and running software without having to go through a whole bunch of setup or installation of dependencies.

![Docker1](images/Docker2.png?raw=true "Title")

![Docker1](images/Docker3.png?raw=true "Title")

### Image

* This is a single file that gets stored on your hard drive and at some point in time it you can use this image to create something called a container.

* A container is an instance of an image and you can kind of think of it as being like a running program.

### Container

* An instance of an image. You can kind of think of it as being like a running program.
* A program with its own isolated set of hardware resources.
* It kind of has its own little set or its own little space of memory has its own little space of networking technology and its own little space of hard drive space as well.
* A container is really a process or a set of processes that have a grouping of resources specifically
assigned to it.

## Operating System Containers

![Operating System Container](images/OS.png?raw=true "Title")

### Kernel

* The kernel is a running software process that governs access between all the programs that are running on your computer and all the physical hardware that is connected to your computer as well.

### Name Spacing

![Name Spacing](images/Namespacing.png?raw=true "Title")

* We can look at all of the different hardware resources connected to our computer and we can essentially
segment out portions of those resources so we could create a segment of our hard disk specifically dedicated
to housing the resources we need.

* We are allowed to isolate resources per a process or a group of processes and we essentially saying that any time a particular process asks for a resource we're going to direct it to this one little specific area of the given piece of hardware.
* It can be also used for software elements as well.

### Control Groups

* Can be used to limit the amount of resources that a particular process can use.
* Can be used to limit the amount of memory that a process can use, the amount of CPQ, the amount of hard drive input input, or the input output and the amount of network bandwidth as well.

![Name Spacing2](images/Namespacing2.png?raw=true "Title")

### Image (File System Snapshot)

![Image and Containers](images/Image-Container.png?raw=true "Title")

* Images contain snapshots (essentially kind of like a copy paste of a very specific set of directories or files) and very specific startup commands.

### Namespacing and Control Groups (cgroups)

* Specifically belong to Linux (not windows or macOS)

### Linux VM hosting different containers

![Linux Virtual Machine](images/Linux-VM.png?raw=true "Title")

## Container Lifecycle

### Creating and running a container from an Image

![Running images](images/Creating-Running-Image.png?raw=true "Title")

### Running a hello world image

![Running hello world command](images/Running-Hello-World.png?raw=true "Title")

### Overriding default run commands

![Overriding default run commands](images/Overriding-Default-Run.png?raw=true "Title")

### Overriding BusyBox default run commands

![Overriding busybox](images/BusyBox-Override.png?raw=true "Title")

### List all running containers

![List all running containers](images/List-All-Running-Containers.png?raw=true "Title")

### Container Status

![Container status](images/Container-Status.png?raw=true "Title")

### Docker run = Docker create + Docker Start

![Docker run create](images/Docker-Run-Create.png?raw=true "Title")

![Docker start ID](images/Docker-Start-ID.png?raw=true "Title")
* In order to actually see information being printed out from the container we had to add `-a`

### Creating and starting a container

![Start Create Containers](images/Start-Create-Container.png?raw=true "Title")

![Start Command](images/Start-Command.png?raw=true "Title")

* The `-a` specifically it is attached to the container  and watch for the output coming from it and printed out at my terminal.

![Reference Container](images/Reference-Container.png?raw=true "Title")

* `docker run`  takes our file system snapshot and gets a reference to it inside the container.

![Startup Command](images/Startup-Command.png?raw=true "Title")

* `echo hi there` starts out as startup command in Busybox Image and makes its way into the running processes in the container.

### Deleting containers completely

* To completely delete a container, run `docker system prune`

![Prune](images/Prune.png?raw=true "Title")

### Getting logs from a container

![Logs](images/Logs.png?raw=true "Title")
* Run `docker create busybox echo hi there` then grab returned id `2d397cab7ed77202385b9ca279fafe72c4f8867c24aaa7474124b7390837d638`.
* It will then take that ID and run `docker start` and `paste the ID` that starts up the container it executes. `echo Hi there` inside of it and then it immediately exits.
* To get logs, we run `docker logs 2d397cab7ed77202385b9ca279fafe72c4f8867c24aaa7474124b7390837d638`