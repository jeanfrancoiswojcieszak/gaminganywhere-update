GamingAnywhere (updated)(compile on ubuntu 2204)
==============

GamingAnywhere: An Open Cloud Gaming System

# Overview

GamingAnywhere is an open-source clouding gaming platform. In addition to its
openness, we design GamingAnywhere for high extensibility, portability, and
reconfigurability. GamingAnywhere currently supports Windows and Linux, and
can be ported to other OS's including OS X and Android.

# Documents

* Official web site: http://gaminganywhere.org/

* Quick start guide: http://gaminganywhere.org/doc/quick_start.html

* Configuration file guide: http://gaminganywhere.org/doc/config.html

* FAQ: http://gaminganywhere.org/faq.html

# Quick Notes

* Recommended development platforms Ubuntu Linux x86_64.

* Required packages on Linux OS (both runtime and development files):
```libx11```, ```libxext```, ```libxtst```, ```libfreetype6```,
```libgl1-mesa```, ```libglu1-mesa```, ```libpulse```,
```libasound2```, ```lib32z1```

* Sample command to install required packages on Ubuntu Linux:
  ```
  apt-get  install patch make cmake g++ pkg-config \
		libx11-dev libxext-dev libxtst-dev libfreetype6-dev \
		libgl1-mesa-dev libglu1-mesa-dev \
		libpulse-dev libasound2-dev lib32z1 libssl-dev libxtst-dev
  ```
* Modify the file env-setup, the GADEPS setting must be the absolute path to the cloned project plus /deps.posix at the end.
  
  Next type:
  
 ```source env-setup```
 
  Next :
  
  ``` cd deps.src```
  
  ``` make```
  
  Next:
  
  ``` cd ../ga```
  
  ``` make```
  
  And finally you will have the linux binaries in "clone of ga project"/bin directory


*Usage:
  
  on the server:
  
  ``` copy "clone of ga project"/bin  and "clone of ga project"/deps.posix on it```

  ``` configure ld to search in deps.posix/lib (as root) :```
  
  ``` echo "<absolute path to deps.posix directory>/lib" > /etc/ld.so.conf.d/ga.conf```
  
  ```ldconfig```
  
  as a normal user:

  ``` ./ga-server-periodic conf/server.desktop.conf```
  
  
  on the client:
  
  ```copy "clone of ga project"/bin and "clone of ga project"/deps.posix on it```
  
  ``` configure ld to search in deps.posix/lib (as root):```
  
  ``` echo "<absolute path to deps.posix directory>/lib" > /etc/ld.so.conf.d/ga.conf```
  
  ```ldconfig```
  
  as a user that is normal:
  
  ```./ga-client conf/client.abs.conf rtsp://"ip of the server":8554/desktop```
  
  
 
  








  
