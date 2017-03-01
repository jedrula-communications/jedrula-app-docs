# jedrula-app-docs
documentation of jedrula's personal application

The application is a combination of a portfolio and a technical blog

The whole system is composed of 3 applications which have seperate repositories

#1. Frontend application - Ember with fastboot addon
####1.1. repository url  
https://github.com/jedrula-communications/personal-project  
####1.2. what
Ember application - there is a fastboot version, see #2 deployed running on Pi and static version on surge.sh
####1.3. access the pure ember - surge version  
http://jedrula-app.surge.sh/
monitor: https://uptimerobot.com/dashboard#778679445

#2. Fastboot server
####2.1. repository url  
https://github.com/jedrula-communications/ember-fastboot-server
####2.2 what
fastboot application which runs the code from #1
####2.3 access
http://78.88.255.144:5000 (port forwarded to a raspberry pi 5000 port running fastboot app)  
monitor: https://siteuptime.com/users/reports.php?Id=4489  
monitor2: https://uptimerobot.com/dashboard.php#778677465


#3. Backend application - nodejs (express + mongodb)  
####3.1. repository url
https://github.com/jedrula-communications/personal-project-backend  
####2.2. what
jsonapi-server used as API for Ember
####3.3. access
not accesible publicly, 192.168.0.185:3000 on LAN (raspberr pi running nodejs app)

#4. Auth application - nodejs jsonwebtoken layer  
####4.1. repository url  
https://github.com/jedrula-communications/jwt-auth  
####4.2. what  
nodejs backend which authorizes requests using jsonwebtokens. authorized requests are proxied to the backend application (2)  
####4.3. access 
http://78.88.253.196:4000/ (port forwarded to a raspberry pi 4000 port running nodejs app)
monitor: https://uptimerobot.com/dashboard.php#778677470
