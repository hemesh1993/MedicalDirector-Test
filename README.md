# MedicalDirector-Test
Technical Test
# 1

For the purpose of creating Centos instance, AWS has been used and the instance created has following opening ports :22 , :80 , :8080

The path Interview --> Playbooks provides information about the playbook to build nginx reverse proxy for apache tomcat server [main.yml].

Provide IP address in the hosts-dev file.

Run the play-book [main.yml].

                                       Command: ansible-playbook    main.yml
                                        Nginx runs on port :80
                                       Tomcat server on port :8080
                                        
In this play-book SSH access has been disabled for the root user and installed a role which provides security related configurations and base-line protection to server.

 To install the role 
 
                                        $ ansible-galaxy install dev-sec.os-hardening

                                 
 # 2 

Interview--> Docker --> nginx --> Docker file:

             
  Docker file is run to build nginx-proxy image with password authentication.
                            
                            build image:
                            command : docker build -t nginx-reverse-proxy .
                           
                            To run image:
                            command : docker run --net=host --rm --name reverse-proxy  nginx-reverse-proxy 
                            
     
     
 Access for non-privileged user
     
 username : admin
     
 password : admin
                            
  
  Interview--> Docker--> docker-compose.yml:
  
 docker-compose.yml file builds image nginx-reverse-proxy and image apache-tomcat and when given proper credentials, redirects to apache tomcat.
                                     
    
                                   command : docker-compose up -d --build
                                   
                                   
     
