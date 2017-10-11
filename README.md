# jedrula-app-docs
documentation of jedrula's personal application

The application is a combination of a portfolio and a technical blog

The whole system is composed of 4 applications which have seperate repositories

# 1. Frontend application - Ember with fastboot addon

#### 1.1. repository url  
https://github.com/jedrula-communications/personal-project

#### 1.2. what
Ember application - there is a fastboot version (see #2) running on Pi and static version on surge.sh

#### 1.3. access the pure ember - surge version  
http://jedrula-app.surge.sh/
monitor: https://uptimerobot.com/dashboard#778679445

# 2. Fastboot server

#### 2.1. repository url  
https://github.com/jedrula-communications/ember-fastboot-server

#### 2.2 what
fastboot application which runs the code from #1

#### 2.3 access
http://jedrula.ddns.net:5005 (port forwarded to a home server 5005 port running fastboot app)  


# 3. Backend application - nodejs (express + mongodb)  

#### 3.1. repository url
https://github.com/jedrula-communications/personal-project-backend  

#### 3.2. what
jsonapi-server used as API for Ember

#### 3.3. access
not accesible publicly, 192.168.1.102:3000 on LAN (raspberry pi running nodejs app)

#### 3.4 mongo
you need to make sure mongo url is set correctly. When you use an ip then make sure bind_ip is set properly in /etc/mongod.conf

# 4. Auth application - nodejs jsonwebtoken layer  

#### 4.1. repository url  
https://github.com/jedrula-communications/jwt-auth  

#### 4.2. what  
nodejs backend which authorizes requests using jsonwebtokens. authorized requests are proxied to the backend application (#3)  

#### 4.3. access 
http://jedrula.ddns.net:4000/ (port forwarded to a raspberry pi 4000 port running nodejs app)




#### How it is hosted
1 (frontend js app) - sits on a surge server, api server points to a no-ip domain which holds the ip of my modem. The api server port is forwarded by my home router to a raspberry pi where the nodejs application is running

2 (fastboot app) - sits on a NAS synology server. Used to live on a raspberry but was very slow. The url is a no-ip server with a port that is forwarded to the NAS.

3 (backend application) - sits on raspberry pi. Not publicly accessible/

4 (auth application) - sits on raspberry pi. It can be accessed using the url of api server from point 1

5 (mongodb) - sits on raspberry pi.
