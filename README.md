# Web server performance tests
This repository contains an isolated Docker environment for exploring and testing the performance of HTTP web servers.

By now, it starts up 3 different services: 
- Apache
- NGINX
- OpenLiteSpeed

### Info
The default test subject page here (<code>html/index.html</code>) is based on: https://github.com/cbracco/html5-test-page
- Sample image by: https://placekitten.com/
- Sample audio by: https://file-examples.com/
- Sample video by: https://www.sample-videos.com/

## Quickstart
- Make sure you have [Docker](https://docs.docker.com/desktop/) installed.
- Startup the container:
```
docker compose up -d
```

The container should start listening in 3 different addresses:
- Apache: http://localhost:8081
- Nginx: http://localhost:8082
- LiteSpeed: http://localhost:8083

## ApacheBench - ab
ApacheBench is a tool designed for benchmarking http servers. You can test the container web servers we just configured with the following commands:
```
ab -n 1000 -c 100 http://localhost:8081/ #apache
ab -n 1000 -c 100 http://localhost:8082/ #nginx
ab -n 1000 -c 100 http://localhost:8083/ #litespeed
```
- <code>-n 1000</code> specifies 1000 requests
- <code>-c 100</code> specifies 100 simultaneos connections

## Other benchmarking tools
I'll setup and test other tools soon. You can contribute by sharing your own tests and tools

## Benchmarking data
I'll share benchmarking data for these tests in <code>/data</code>. You can contribute by sharing your own data (along with your computer's specs) via a pull request.
