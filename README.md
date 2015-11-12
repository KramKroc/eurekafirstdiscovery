# eurekafirstdiscovery
Project that shows behaviour of config client defaulting to localhost:8888 when discovery &amp; config servers 
not contactable in eureka first discovery.

# Versions

| Component | Version|
|-----------|--------|
| Docker Toolbox | 1.9.0 |
| Spring Boot | 1.3.0-RC1 |

# Build and Run

In the root folder run the following command which will build you docker images for you:

```sh
$ ./gradlew clean buildDocker
```

*Note:* You need to run the above command in a docker quickstart terminal.

After that you can bring up the images using docker-compose:

```sh
$ docker-compose up
```

It can be hard to follow the logs as all three services output at the same time so you can possibly use 
Kitematic to look at the individual logs for the sample-service. When run you can see entries like the 
following when the discovery and config servers are still coming up):

```log
2015-11-12 14:59:16.165  WARN 1 --- [           main] com.netflix.discovery.DiscoveryClient    : Can't get a response from http://discoveryservice:8761/eureka/apps/
   :
2015-11-12 14:59:17.740  WARN 1 --- [           main] lientConfigServiceBootstrapConfiguration : Could not locate configserver via discovery
   :
2015-11-12 14:59:19.359  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-11-12 14:59:21.078  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-11-12 14:59:22.338  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-11-12 14:59:23.712  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-11-12 14:59:25.208  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-11-12 14:59:26.828  INFO 1 --- [           main] c.c.c.ConfigServicePropertySourceLocator : Fetching config from server at: http://localhost:8888
2015-1
```
