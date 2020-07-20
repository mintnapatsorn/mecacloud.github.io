---
layout: tutorial
title: Git webhook
---
## Git Webhook

* ### What's git Webhook 💻

  When you push your projects to git repository but the deployment that's did't change content inside the conatainer. You can use this tutorial for resolve its.  

* ### How to start ?

 1. Firstly,create `new workload` and choose `Stateful Set` 
    ![stateful_set](/assets/webhook/statefull.png)
    <br><br>
 2. create new container that's have [webhook](https://hub.docker.com/r/maxoatzadn/webhook) image inside.
    <br>
    `Container Name`: <"Your container name"> <br>
    `Image Name`: "maxoatzadn/webhook" <br>
    `Port`: "80"
    <br><br>
    
    > Hint: Port 80 is default port of nginx.
  
    <br><br> 
    
 2. fill Enviroment Varible with your [GitHub](https://github.com/) clone with Https for application's contents to container.
 
  
 3.
 4.
