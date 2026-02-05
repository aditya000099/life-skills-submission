# Scaling and Need for Load Balancer

### Introduction

I investigated our current performance issues. The team lead asked me to look into scaling solutions. I studied how we can handle more traffic. There are two main ways to solve this problem.

### Types of Scaling

I found there are two different ways to scale our application.

### Vertical Scaling

This is also called scaling up. It means we increase the power of our current server. We can add more RAM or a faster CPU to our existing vm.

* **Pros-** It is very simple to do. We do not need to change our code.
* **Cons-** There is a limit to how much we can upgrade one machine. It is also expensive. Also if this machine goes down, we need to wait till it comes up again. Powerful Server != No Downtime (especially in case of outage by cloud provider in a specific region).

### Horizontal Scaling

This is also called scaling out. This means we add more servers to our system. Instead of one big server, we use three or four smaller ones.

* **Pros:** We can keep adding servers forever. If one server breaks, the others stay online.
* **Cons:** It is more complex to manage. We need to sync data between the servers.

### Load Balancers

If we choose horizontal scaling, we need a load balancer. A load balancer just distributes the traffic to different servers depending on teh load on one server and also reduces latency for different country users, thus improving the loading time. It accepts requests from users and sends them to the best available server.

I learned about these common methods for distributing traffic:

1. Round Robin- The load balancer takes turns sending requests to each server.
2. Least Connections- It sends the new user to the server doing the least amount of work right now.

### Conclusion

I recommend we use horizontal scaling. Vertical scaling is a temporary fix, but we will hit a wall soon. Horizontal scaling takes more work now, but it is better for the future.

### References

* Nginx- What is Load Balancing - [https://www.nginx.com/resources/glossary/load-balancing/](https://www.nginx.com/resources/glossary/load-balancing/)
* DigitalOcean- Understanding Horizontal vs Vertical Scaling - [https://www.digitalocean.com/community/tutorials/horizontal-vs-vertical-scaling](https://www.google.com/search?q=https://www.digitalocean.com/community/tutorials/horizontal-vs-vertical-scaling)
* AWS- [https://aws.amazon.com/what-is/load-balancing/](https://aws.amazon.com/what-is/load-balancing/)
