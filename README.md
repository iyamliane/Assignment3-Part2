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
4) Add the tag "web" under "tags" 
5) Repeat the same steps above with a second droplet