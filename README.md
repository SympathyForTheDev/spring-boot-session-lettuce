# spring-boot-session-lettuce
Spring Boot Demo project Integration of Spring Security with Spring Session and Lettuce

=== Setting Up a Redis Server

The server is available for free here https://redis.io/download

Follow the installation instruction and then start the server:

```shell
$ redis-server
```

=== Run the Sample Application

With Gradle
```shell
$ ./gradlew clean bootRun
```

=== Test the application

- Open the browser and access the application at http://localhost:2222/login
- Login with credential "admin/password"
- Logout at http://localhost:2222/logout

=== Dependency 

+-----------+        +-----------+        +-----------+        +-----------+

|           |        |           |        |           |        |           |

| Spring    |        |  Spring   |        |  Spring   |        |           |

| Session   +------->+  Session  +------->+  Data     +------->+  Lettuce  |

| Core      |        |  Redis    |        |  Redis    |        |           |

|           |        |           |        |           |        |           |

+-----------+        +-----------+        +-----------+        +-----------+


1/ spring-session-core: provide the httpSession support 

2/ spring-session-redis: annotation @EnableRedisHttpSession and spring autoconfiguration

3/ spring-data-redis: repository layer 

4/ lettuce: redis client 

=== Limitations 

This implementation is for Spring Boot 1.5.x with some limitations because it's not possible to use the latest version of lettuce (5.x and above)
And the compatible lettuce version (3.5.0.Final) is only compatible with spring session 1.3.x (and not with the new 2.x.x)

If you need to use the latest version of lettuce or the latest version of spring-session you have to use Spring Boot 2 (since version 2.0.0.M7)

All the details here :
https://github.com/spring-projects/spring-boot/issues/9536


