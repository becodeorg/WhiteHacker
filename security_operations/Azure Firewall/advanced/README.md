# Azure Load Balancer
Type of challenge : **Learning/Practice**

Duration : **10 hour**

Team Challenge : **solo**

## Introduction

Becloud starts to grow and have more and more important client. For those big clients, high availability is crucial. They need to be up 24/7. Since we saw some issues on the main production server, we will deploy a second server and a load balancer.

### Learning objective
- Understand High Availability
- Deploy a Load Balancer

## Your mission

Your mission is to deploy a load balancer on Azure. Follow the following steps :
- Create 2 virtual machines (windows/linux)
- Install web server on the VM (apache, nginx, iis)
- Create a new webpage showing the name of the server answering the request
- Create a load balancer
    - Create a pool
    - Create probe
    - Create load balancing rules
- Try out through the public IP

Following your configuration, you will receive alternatively the name of one of the web servers when trying to reach your load balancer.

## Trusty Resources
- [Azure LB](https://docs.microsoft.com/en-gb/azure/load-balancer/)
- [Tutorial - create a LB](https://docs.microsoft.com/en-gb/azure/load-balancer/tutorial-load-balancer-standard-public-zone-redundant-portal)
- [SNAT](https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-outbound-connections)