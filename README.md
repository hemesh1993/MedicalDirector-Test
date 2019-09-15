# MedicalDirector-Test
Technical Test
# 1

In this AWS has been used to create Centos instance with opening ports :22 , :80 , :8080

Interview/playbooks provides information about the ansible-playbook to build nginx reverse proxy for apache tomcat server.[main.yml]

Provide Ip address in the [hosts-dev file]

Run the play-book[main.yml]

                                       Command: ansible-playbook    main.yml
                                       Nginx runs on port :80
                                       Tomcat server on port :8080
                                        
In this play-book "SSH access has been disabled for the root user"  and installed a role which provides security related configurations and base-line protection to server

 To install the role 
 
                                        $ ansible-galaxy install dev-sec.os-hardening

This Role provides
            
                      It configures:

                                 Configures package management e.g. allows only signed packages
                                 Remove packages with known issues
                                 Shadow password suite configuration
                                 Configures system path permissions
                                 Disable core dumps via soft limits
                                 Restrict root Logins to System Console
                                 Set SUIDs
                                 Configures kernel parameters via sysctl
                                 Install and configure auditd
                                 
 # 2 

Docker folder :
             
  docker file which build nginx-proxy image with password authentication.
                            
                            build image:
                            command : docker build -t nginx-reverse-proxy .
                           
                            To run image:
                            command : docker run --net=host --rm --name nginx-reverse-proxy reverse-proxy 
                            
     
   docker-compose.yml  file  which builds image nginx-reverse-proxy and image tomcat which redirect to apache tomcat.
                                     
    
                                   command : docker-compose up -d
                                   
     
