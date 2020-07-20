---
layout: tutorial
title: Git webhook
---
## Git Webhook

* ### What's git Webhook 💻

  When you push your projects to git repository but the deployment that's did't change content inside the conatainer. You can use this tutorial for resolve its.  

* ### How to start ?

 1. Firstly,create `new workload` and choose `Stateful Set` 
    <p align="left">
      <img src="/assets/git_webhook/statefull.png">
    </p>
    <br>
 2. Fill `Stateful Set Name` and `Service Name`.
     <br><br>
     <img src="/assets/git_webhook/stateful2.png">
     <br><br>
 3. create new container that's have [webhook](https://hub.docker.com/r/maxoatzadn/webhook) image inside.
    <br>
    `Container Name`: <"Your container name"> <br>
    `Image Name`: "maxoatzadn/webhook" <br>
    `Ports`:<br>
     &nbsp; &nbsp; &nbsp; &nbsp;-`Name`: <"Name container port"><br>
     &nbsp; &nbsp; &nbsp; &nbsp;-`Port`: "80"
    
    <br>
    
    > Hint: Port 80 is default port of nginx.
    
    ![container1](/assets/git_webhook/container1.png)
    
    <br>
    
 4. fill Enviroment Varible with your [GitHub](https://github.com/) clone with Https for application's contents to container.
    <br>
     `Environment Variable`:<br>
     &nbsp; &nbsp; &nbsp; &nbsp;-`Key`: "LOCATION"<br>
     &nbsp; &nbsp; &nbsp; &nbsp;-`Value`: <"Your project on github"> <br>
     &nbsp; &nbsp; &nbsp; &nbsp;(eg. https://github.com/toptapznt/nginx-test.git)
    <br><br>
    ![container2](/assets/git_webhook/container2.png)
  
    <br>
    
 5. create new service that's target to your container and select service name that's same as previous part. <br><br>
    `Service Name` : <"Your service name"> <br><br>
     select : `Label` <br><br>
    `Selector`: select container that's your create.
    `Ports`:<br>
    &nbsp; &nbsp; &nbsp; &nbsp;-`Name`: <"Name service port"><br>
    &nbsp; &nbsp; &nbsp; &nbsp;-`Service Port`: "80" <br><br>
    ![service1](/assets/git_webhook/service1.png)
    
    <br>
    
 6. create new volume, type `Config Map`. <br>
    `Volume Name`: <"Your Volume name"> <br>
    `ConfigMap Name`: <"Your ConfigMap name"><br>
    then click `Add New Config Map`
    ![volume3](/assets/git_webhook/voulme3.png)
    
    <br>
    
 7. Insert new ConfigMap data that's for change config file of nginx. 
    `Key`: "default.conf" <br>
    `Content`: at below <br><br>
    ```
    # default.conf
    server {
    listen       80;
    server_name  localhost;

    location / {
        root   /App;
        index  index.nginx-debian.html;
    }
    
    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   /usr/local/openresty/nginx/html;
    }

    location /_hook {
        default_type text/html;
        content_by_lua_block {
            os.execute("/myShellScript.sh")
            ngx.say("<p>pull complete !!</p>")
        } 
    }
    }
    ```
    <br>
    
    ![volume4](/assets/git_webhook/voulme4.png)
    ![volume6](/assets/git_webhook/volume6.png)
 4.
