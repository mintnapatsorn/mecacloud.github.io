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
    <!--![stateful_set](/assets/git_webhook/statefull.png)-->
 2. Fill `Stateful Set Name` and `Service Name`.
     <br><br>
     <img src="/assets/git_webhook/stateful2.png">
 3. create new container that's have [webhook](https://hub.docker.com/r/maxoatzadn/webhook) image inside.
    <br>
    `Container Name`: <"Your container name"> <br>
    `Image Name`: "maxoatzadn/webhook" <br>
    `Ports`:<br>
       `Name`: "<Name container port>"<br>
       `Port`: "80"
    
    <br>
    
    > Hint: Port 80 is default port of nginx.
    
    ![container1](/assets/git_webhook/container1.png)
    
 4. fill Enviroment Varible with your [GitHub](https://github.com/) clone with Https for application's contents to container.
    <br>
     `Environment Variable`:<br>
        `Key`: "LOCATION"<br>
        `Value`: "<Your project on github>"
        (eg. https://github.com/toptapznt/nginx-test.git)
    <br>
    ![container2](/assets/git_webhook/container2.png)
  
    <br><br> 
    
 4. 
 
  
 3.
 4.
