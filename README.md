
# Project Title

# Performance_Testing

Testing Site - "https://restful-booker.herokuapp.com"

# Introduction

This document explains how to run a performance test with JMeter against a   Booking.



# Installations
Java
```bash
  https://www.oracle.com/java/technologies/downloads/
```
JMeter  
```
https://jmeter.apache.org/download_jmeter.cgi
```
Click =>Binaries  
=>apache-jmeter-5.6.3.zip

We use BlazeMeter,Lighthouse to generate JMX files

https://chrome.google.com/webstore/detail/blazemeter-the-continuous/mbopgmdnpcbohhpnfglgohlbhfongabi?hl=en,

https://chromewebstore.google.com/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk


# Prerequisites

- As of JMeter 5.6, Java 8+ and above are supported.
- we suggest multicore cpus with 4 or more cores.
- Memory 16GB RAM is a good value.

# Elements of a minimal test plan

- Thread Group

    The root element of every test plan. Simulates the (concurrent) users and then run all requests. Each thread simulates a single user.

- HTTP Request Default (Configuration Element)

- HTTP Request (Sampler)

- Summary Report (Listener)

# Test Plan
Testplan > Add > Threads (Users) > Thread Group (this might vary dependent on the jMeter version you are using)

- Name: Users

- Number of Threads (users): 1 to 30

- Ramp-Up Period (in seconds): 3

- Loop Count: 3

  i. The general setting for the tests execution, such as whether Thread Groups will run simultaneously or sequentially, is specified in the item called Test Plan.

  ii. All HTTP Requests will use some default settings from the HTTP Request, such as the Server IP, Port Number, and Content-Encoding.

  iii. Each Thread Group specifies how the HTTP Requests should be carried out. To determine how many concurrent "users" will be simulated, one must first know the number of threads. The number of actions each "user" will perform is determined by the loop count.

  iv. The HTTP Header Manager, which allows you to provide the Request Headers that will be utilized by the upcoming HTTP Requests, is the first item in Thread Groups.


# Test execution (from the Terminal)

- keep your jmx file in bin
- JMeter should be initialized in non-GUI mode.
- Make a report folder in the bin folder.
- Run Command in jmeter\bin folder

# Command

Jtl file generate command

```
jmeter -n -t Booking.jmx -l report\Booking.jtl
jmeter -n -t Ecommerce.jmx -l report\Ecommerce.jtl
```

Report Generate command

```
jmeter -g report\Booking.jtl -o report\Booking.html
jmeter -g report\Ecommerce.jtl -o report\Ecommerce.html
```
## Screenshots

```
Booking
```

![booking](https://github.com/user-attachments/assets/046e7466-fe3b-4c20-804a-1e7e0ff6b212)
![b](https://github.com/user-attachments/assets/24736540-833f-4d7a-bf77-83ad6307da10)

```
Ecommerce
```
![eommerce-1](https://github.com/user-attachments/assets/cb270551-0cda-4cf4-8019-ff76250ae2db)
![ecommerce](https://github.com/user-attachments/assets/2ef412ca-96fc-4de8-b868-9681ade86192)

