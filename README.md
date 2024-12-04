# ACIT 2420 Assignment3-Part2 #

## Introduction ##
For this assignment we will be expanding our knowledge on Nginx by configuring two servers along with a load balancer to distribute traffic among the servers. We will using DigitalOcean to create the droplets that run on Arch Linux. 

Load balancers distribute traffic across multiple servers to improve performance and reliability, while Nginx is a very useful tool that can serve web content, act as a reverse proxy, and balance loads efficiently.


## Table of Contents ## 

## Task 1: Create Two New Droplets ##
We will be creating two new droplets for our Arch Linux servers using DigitalOcean along with the tag ```web```. These tags will be utilized when creating your load balancer.

1) Click on green "Create Droplet" button 
2) Choose "SFO3" for region and datacenter
3) Use the custom image (that we used for Assignment1) for Arch Linux as OS
4) Add the tag ```web``` under "tags" 
5) Repeat the same steps above with a second droplet

## Task 2: Create Load Balancer ##

We will be creating a load balancer for the purpose of distributing traffic between our two Arch Linux servers. 

1) Click on "Load Balancer" on the side navigation menu
2) Click on "Create Load Balancer"
3) Choose "SFO3" for region and datacenter
4) Choose "External (public)" for type
5) Use the ```web ``` tag 

## Task 3: Clone Starter Code Repoistory ## 

Now we will clone the provided *updated* starter code from a repository. This will contain the new generate_index script that will generate an updated HTML script. 

1) SSH into your server and run the following command:

```git clone http://git.sr.ht/~nathan_climbs/2420-as3-p2-start```

2) Create a system user: 

```sudo useradd -r -d /var/lib/webgen -s /usr/sbin/nologin webgen```

3) Create directory for the user:

```sudo mkdir -p /var/lib/webgen```

```sudo mkdir -p /var/lib/webgen/bin /var/lib/webgen/HTML /var/lib/webgen/documents```


4) Move script to directory:

```sudo mv 2420-as3-p2-start/generate_index /var/lib/webgen/bin/```

5) Give execute permissions for script:

```sudo chmod +x generate_index```

6) Create document files: 

```sudo touch /var/lib/webgen/documents/file-one /var/lib/webgen/documents/file-two```

Your file structure should look like this: 
```
/var/bin/webgen/
 .
 ├── bin/
 │   └── generate_index
 ├── documents/
 │   ├── file-one
 │   └── file-two
 └── HTML/
 ```

7) Change ownership for the system user: 

```sudo chown -R webgen:webgen /var/lib/webgen```

8) Repeat above steps for your other server

## Task 4: Nginx Server Configuration ##

Server blocks configure web servers to handle requests for specific domains or paths, defining document roots and settings for each site.

>[!NOTE] 
>For this task, we will be configurating the servers on both droplets. Ensure that you repeat each of the steps below for the other existing server.


