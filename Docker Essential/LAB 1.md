[Skip to main content](https://courses.cognitiveclass.ai/xblock/block-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@vertical+block@7cca446bd64348f88404131129441a67?show_title=0&show_bookmark_button=0&recheck_access=1&view=student_view#main)
#lab 
### Run a container

Use the Docker CLI to run your first container.

1. Open a terminal on your local computer and run this command:
    ``
    $ docker container run -t ubuntu top
    
    You use the `docker container run` command to run a container with the Ubuntu image by using the `top` command. The `-t` flag allocates a pseudo-TTY, which you need for the `top` command to work correctly.
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/bf022dd72d1aa447158850d795cc82bb/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step1_1.png)
    
    The `docker run` command first starts a `docker pull` to download the Ubuntu image onto your host. After it is downloaded, it will start the container. The output for the running container should look like this:
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/d11940751dd3b0de71cab372cfccd284/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step1_2.png)
    
    `top` is a Linux utility that prints the processes on a system and orders them by resource consumption. Notice that there is only a single process in this output: it is the `top` process itself. You don't see other processes from the host in this list because of the PID namespace isolation.
    
    Containers use Linux namespaces to provide isolation of system resources from other containers or the host. The PID namespace provides isolation for process IDs. If you run `top` while inside the container, you will notice that it shows the processes within the PID namespace of the container, which is much different than what you can see if you ran `top` on the host.
    
    Even though we are using the Ubuntu image, it is important to note that the container does not have its own kernel. It uses the kernel of the host and the Ubuntu image is used only to provide the file system and tools available on an Ubuntu system.
    
2. Open a new terminal. To open a new terminal connected to **node1** by using Play-With-Docker.com, click **Add New Instance** on the left and then **ssh** from **node2** into **node1** by using the IP that is listed by node1, for example:
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/71523c56a5b7544646b38bf37e8dd9a7/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step1_3a.png)
    
3. In the new terminal, get the ID of the running container that you just created:
    
    docker container ls 
     
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/6a826f45cab3ae2dd0c6bddcd3a4eaea/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step1_3.png)
    
4. Use that container ID to run `bash` inside that container by using the `docker container exec` command. Because you are using bash and want to interact with this container from your terminal, use the `-it` flag to run using interactive mode while allocating a psuedo-terminal:
#command
    
    $ docker container exec -it b3ad2a23fab3 bash 
    root@b3ad2a23fab3:/#
    
    You just used the `docker container exec` command to enter the container's namespaces with the bash process. Using `docker container exec` with `bash` is a common way to inspect a Docker container.
    
    Notice the change in the prefix of your terminal, for example,  `root@b3ad2a23fab3:/`. This is an indication that you are running bash inside the container.
    
    **Tip:** This is not the same as using ssh to a separate host or a VM. You don't need an ssh server to connect with a bash process. Remember that containers use kernel-level features to achieve isolation and that containers run on top of the kernel. Your container is just a group of processes running in isolation on the same host, and you can use the command `docker container exec` to enter that isolation with the `bash` process. After you run the command `docker container exec`, the group of processes running in isolation (in other words, the container) includes `top` and `bash`.
    
5. From the same terminal, inspect the running processes:
    
    $ ps -ef
     
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/6ccbf68f05efd96cb645ab4f4ea30c40/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step1_3b.png)
    
    You should see only the `top` process, `bash` process, and your `ps` process. PID is just one of the Linux namespaces that provides containers with isolation to system resources.
    
    Other Linux namespaces include:
    
    - MNT: Mount and unmount directories without affecting other namespaces.
    - NET: Containers have their own network stack.
    - IPC: Isolated interprocess communication mechanisms such as message queues.
    - User: Isolated view of users on the system.
    - UTC: Set hostname and domain name per container.
    
    These namespaces provide the isolation for containers that allow them to run together securely and without conflict with other containers running on the same system.
    
6. For comparison, exit the container and run `ps -ef` or `top` on the host. These commands will work on Linux or Mac. For Windows, you can inspect the running processes by using `tasklist`.
    
    root@b3ad2a23fab3:/# exit 
    exit
    
    In the next lab, you'll see different uses of containers and the benefit of isolation as you run multiple containers on the same host.
    
    **Tip:** Namespaces are a feature of the Linux kernel. However, Docker allows you to run containers on Windows and Mac. The secret is that embedded in the Docker product is a Linux subsystem. Docker open-sourced this Linux subsystem to a new project: [LinuxKit](https://github.com/linuxkit/linuxkit). Being able to run containers on many different platforms is one advantage of using the Docker tooling with containers.
    
    In addition to running Linux containers on Windows by using a Linux subsystem, native Windows containers are now possible because of the creation of container primitives on the Windows operating system. Native Windows containers can be run on Windows 10 or Windows Server 2016 or later.
    
7. Clean up the container running the `top` processes:
    
    <ctrl>-c