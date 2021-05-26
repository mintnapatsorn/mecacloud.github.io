---
layout: tutorial
title: Basic Deploy Website Application in MECA
---
## Build basic website application in MECA with one service

When you build or deploy website in your computer, you cahttps://www.elastic.co/guide/en/siem/guide/7.7/detection-engine-overview.html#detections-permissionsn only the once who can access the file. When you upload the file to docker hub ,anybody can be access your local file that will be unsecure for your computer. MECAs will helps to deploy website in namespace and have its own memory,resource,CPU and RAM. You can build any kind of website by using container or images in docker hub that suited to your website or idea then deploy it in MECA. You can also deploy more than one images at a time, to make website application fully successful.

- **For this project we will shown the basic jekyll site**

- **In this tutorial will only deploy 1 website 1 service**

**1.** Click the workload tab in menubar and you will get the page like this. This page will shown all of the project website that deployed on your namespace,you can see whether its deployed successful or not. This page also show the project status too.

![Workloadpage](/assets/workloadpage.jpg)

**2.** Click **`+ NEW workload`** to start new project deploy

![New workload](/assets/Newworkload.jpg)

- **This workload can be edit later**

**3.** Name the project on top of page and in deployment part, its have to be the same name and will shown in namespace

![Nameproject](/assets/nameproject.jpg)

**4.** In container part, type in the container name and docker images that come from repository of docker hub ,it can be your images or other images that share on docker hub.

**4.1** If you already have your own image of jekyll site in this tutorial you can use your images repository. Type in the images on general deployment   

![Ownimages](/assets/ownimages.jpg)
 
**4.1.1** If you don't have your own image, find it in docker hub repository and get the name of images.

![finddockerimages](/assets/finddockerimages.jpg)

**4.2** Port of the website, the name of the port will be free to create but the port number have to use the number that you run the website. Example like you run website on https://localhost:4000 you have to type port number 4000.

![PortWebsite](/assets/portwebsite.jpg)

**5.** Before you Deploy, you have to add the service to your website make the website can run on MECA easily. Click the service tab in menu bar on the left hand side. This page will be shown

![Servicetab](/assets/servicetab.jpg)

**5.1** If your website using http or https you have to check the checkbox of the service.

![Servicepagecheck](/assets/servicepagecheck.jpg)

**5.2** Select the deployment the same name with the name of the project

![NameDeployservice](/assets/NameDeployservice.jpg)

**5.2.1** type in project name and port number. Port number that you type in have to port number of your images inside container likes http:80 , https:443 or mysql:3306
 
 - **http/https will be automatically generate website easily**

![PortNumberService](/assets/PortNumberService.jpg)

**6.** Click **`Deploy`** to deploy the project. Make sure that your port is correct, if not it will not run.

![ClickDeploy](/assets/clickdeploy.jpg)

**7.** When you already click **`Deploy`** the project, your project name will be shown on your namespace portal.

![Portalproject](/assets/portalproject.jpg)

**8.** Click your project name and see the progress steps it will take 2-3 minutes to deploy the website

![ClickProjectName](/assets/clickprojectname.jpg)

- You can click edit to change the detailed of the project and then save the workload

![EditWorkload](/assets/editworkload.jpg)

***The time that use to deploy will be depend on docker images or base images size***.
***If you previously deploy website by using this images it will take time shorter than the newer images***.

**8.1** Waiting for progessing website application

![WorkloadProgess](/assets/workloadprogess.jpg)

**8.2** Success deploy the website

![WorkloadSuccess](/assets/workloadsuccess.jpg)

**8.3** This deploy website error, can't be deploy, it take a long time to deploy or you didn't know why website is not run. You can check by Click **`Log`**

![Logerror](/assets/serviceerror.jpg)

**9.** When your status of your website has successfully deploy, you can access the website by subdomain that generate from MECA by using **`Service name.name space.port name.meca.in.th`**  or click the service part in project page 

![Servicetowebsite](/assets/servicetowebsite.jpg)

**It will shown your website**

![Fullywebsite](/assets/fullywebsite.jpg)



