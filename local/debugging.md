#### Q: Container is running and I see it running on port 8888 but when i go to localhost:8888 in my browser is says site cannot be reached:​

#### A: If the container is running, but you're unable to access it from localhost:8888 in your browser, there are a few things you can check and troubleshoot:

(1) Check Port Mapping:  
Confirm that you've mapped the port correctly when running the container. In your docker run command, you should have something like -p 8888:80. This maps port 80 inside the container to port 8888 on the host.

```
docker run -d -p 8888:80 --name hello-world-app my-hello-world-app
```
