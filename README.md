# php-redis-counter
A PHP application that saves the time a person have visited a webpage in Redis and is K8s ready

# How to

## Prerequisites:
To be able to completely do this excersice you need to have:
- A running K8s, K3s, etc. cluster.
- An ingress controller (I have used K8s nginx ingress)
- A load balancer for K8s (I have used Metallb)

## Application
A hit counter is an application that records and indicates the number of visits your web page has received. The counter starts from 1 and is incremented once every time a web page is visited.
To keep track of the visits, the hit counter application requires a form of a database. While disk-based database management systems like MySQL can work, an in-memory database is better in terms of speed, performance, scalability, simplicity, and ease of use. This is where the Redis server comes into play. Redis stores data in your computer’s RAM instead of hitting the disk every time you’re performing an input/output operation. This increases the throughput significantly.

## Databse
To track your site visits, you require a Redis hash map. This is a data structure that implements a key-value pair. A hash map provides a hash table that maps keys to values. Once a user visits your web page, you create a key based on their public IP address or username (for authenticated users), and then you initialize their total visits to a value of 1. Then, every time the user revisits your web page, you check their total visits from the Redis hash map based on their IP address/username and increment the value.
