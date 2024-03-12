#lab 
[Skip to main content](https://courses.cognitiveclass.ai/xblock/block-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@vertical+block@e5e3413f5eab4f2ab11cda4e4bd421be?show_title=0&show_bookmark_button=0&recheck_access=1&view=student_view#main)

It is recommended to use **Docker Personal** edition for this lab practice.

1. Explore the [Docker Hub](https://hub.docker.com/explore/).
    
    The Docker Hub is the public central registry for Docker images. Anyone can share images here publicly. The Docker Store contains community and official images that can also be found on the [Docker Hub](https://hub.docker.com/explore/).
    
    When searching for images, you will find filters for Store and Community images. Store images include content that has been verified and scanned for security vulnerabilities by Docker. Go one step further and search for Certified images that are deemed enterprise-ready and are tested with Docker Enterprise Edition.
    
    It is important to avoid using unverified content from the Docker Store when you develop your own images that are intended to be deployed into the production environment. These unverified images might contain security vulnerabilities or possibly even malicious software.
    
    In the next step of this lab, you will start a couple of containers by using some verified images from the Docker Store: NGINX web server and Mongo database.
    
2. Run an NGINX server by using the [official NGINX image](https://store.docker.com/images/nginx) from the Docker Store:
    
    $ docker container run --detach --publish 8080:80 --name nginx nginx
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/b58bd15bf6d3a19496c79de68f098d8a/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step2_2.png)
    
    You are using a couple of new flags here. The `--detach` flag will run this container in the background. The `publish` flag publishes port 80 in the container (the default port for NGINX) by using port 8080 on your host. Remember that the NET namespace gives processes of the container their own network stack. The `--publish` flag is a feature that can expose networking through the container onto the host.
    
    How do you know port 80 is the default port for NGINX? Because it is listed in the [documentation](https://store.docker.com/images/nginx) on the Docker Store. In general, the documentation for the verified images is very good, and you will want to refer to it when you run containers using those images.
    
    You are also specifying the `--name` flag, which names the container. Every container has a name. If you don't specify one, Docker will randomly assign one for you. Specifying your own name makes it easier to run subsequent commands on your container because you can reference the name instead of the id of the container. For example, you can specify `docker container inspect nginx` instead of `docker container inspect 5e1`.
    
    Because this is the first time you are running the NGINX container, it will pull down the NGINX image from the Docker Store. Subsequent containers created from the NGINX image will use the existing image located on your host.
    
    NGINX is a lightweight web server. You can access it on port 8080 on your localhost.
    
3. Access the NGINX server on http://localhost:8080.  
      
    ![](https://courses.course-dev.skills.network/asset-v1:IBM+CO0101EN+v1+type@asset+block@lab1-step2-3-dwc017-nginx.png)
4. Run a MongoDB server. You will use the [official MongoDB image](https://store.docker.com/images/mongo) from the Docker Store. Instead of using the `latest` tag (which is the default if no tag is specified), use a specific version of the Mongo image: 3.4.
    
    $ docker container run --detach --publish 8081:27017 --name mongo mongo:3.4
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/3533b14b9ce71308e14fe2369b2866a8/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step2_4.png)
    
    Again, because this is the first time you are running a Mongo container, pull the Mongo image from the Docker Store. You use the `--publish` flag to expose the 27017 Mongo port on your host. You must use a port other than 8080 for the host mapping because that port is already exposed on your host. See the [documentation](https://github.com/docker-library/docs/blob/master/mongo/README.md) on the Docker Store to get more information about using the Mongo image.
    
5. Access http://localhost:8081 to see some output from Mongo.  
      
    ![](https://courses.course-dev.skills.network/asset-v1:IBM+CO0101EN+v1+type@asset+block@lab1-step2-5-dwc017-mongo.png)
6. Check your running containers:
    
    $ docker container ls 
    
    ![](https://courses.cognitiveclass.ai/assets/courseware/v1/ec058e1749f07f19c084b55d0003a69e/asset-v1:IBMDeveloperSkillsNetwork+CO0101EN+v1+type@asset+block/lab1_step2_6.png)
    
    You should see that you have an NGINX web server container and a MongoDB container running on your host. Note that you have not configured these containers to talk to each other.
    
    You can see the nginx and mongo names that you gave to the containers and the random name (in this example, priceless_kepler) that was generated for the Ubuntu container. You can also see that the port mappings that you specified with the `--publish` flag. For more information on these running containers, use the `docker container inspect [container id]` command.
    
    One thing you might notice is that the Mongo container is running the `docker-entrypoint` command. This is the name of the executable that is run when the container is started. The Mongo image requires some prior configuration before kicking off the DB process. You can see exactly what the script does by looking at it on [GitHub](https://github.com/docker-library/mongo/blob/master/docker-entrypoint.sh). Typically, you can find the link to the GitHub source from the image description page on the Docker Store website.
    
    Containers are self-contained and isolated, which means you can avoid potential conflicts between containers with different system or runtime dependencies. For example, you  can deploy an app that uses Java 7 and another app that uses Java 8 on the same host. Or you can run multiple NGINX containers that all have port 80 as their default listening ports. (If you're exposing on the host by using the `--publish` flag, the ports selected for the host must be unique.) Isolation benefits are possible because of Linux namespaces.
    
    **Remember**: You didn't have to install anything on your host (other than Docker) to run these processes! Each container includes the dependencies that it needs within the container, so you don't need to install anything on your host directly.
    
    Running multiple containers on the same host gives us the ability to use the resources (CPU, memory, and so on) available on single host. This can result in huge cost savings for an enterprise.
    
    Although running images directly from the Docker Store can be useful at times, it is more useful to create custom images and refer to official images as the starting point for these images. You'll learn to build your own custom images in the next lab.