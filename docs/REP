# REPORT

This document contains a brief of how the following activities have been accomplished:

- The two services `accounts (2222)` and `web` are running and registered (two terminals, logs screenshots).
- The service registration service has these two services registered (a third terminal, dashboard screenshots)
- A second `accounts` service instance is started and will use the port 4444. This second `accounts (4444)` is also
  registered (a fourth terminal, log screenshots).
- What happens when you kill the service `accounts (2222)` and do requests to `web`?  
  Can the web service provide information about the accounts again? Why?

## Steps

The registration server is exposed in `http://localhost:1111`.

![1.png](./resources/1.png)

The account service is exposed in `http://localhost:2222`.
![2.png](./resources/2.png)

We can see that the account service is registered in the registration server:

![3.png](./resources/3.png)

Next, we launch the third application, the web one, at port 3333.

![4.png](./resources/4.png)

We can see that these two services are registered in the registration server:

![5.png](./resources/5.png)

Now we change the port of the account service to 4444 for example:

```yaml
spring:
  application:
    name: accounts-service  # Identify this application
# HTTP Server
server:
  port: 4444   # HTTP (Tomcat) port
```

Then we launch the new account service:

![6.png](./resources/6.png)

There are three services registered in the registration server now:

![7.png](./resources/7.png)

Now we shut down the account service at port 2222:

![8.png](./resources/8.png)


When we try to fetch an account, the request keeps working:

![9.png](./resources/9.png)

This happens because the web server searches for the account service in the Eureka server (where all the services are registered), and it finds the account service in the port 4444 so everything is still working even thought we have killed the accounts service on port 2222.
