## Steps to create Jenkins with Docker:
- Docker file for creating docker instance 
`chmod 777 /root/Jenkins`
`docker run -dit --restart -p 8080:8080 -p 50000:50000 -v /root/Jenkins:/var/jenkins_home jenkins`

##### for passwd
cat /root/Jenkins/secrets/initialAdminPassword

#### URL to do quick action
<localhost>:8080/reboot
<localhost>:8080/cli
