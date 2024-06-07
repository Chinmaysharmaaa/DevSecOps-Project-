# DevSecOps-Project-
Introduction

From a startup to a multinational corporation the software development industry is currently dominated by agile frameworks and product teams and as part of it DevOps strategies. It has been observed that during the implementation, security aspects are usually neglected or are at least not sufficient taken account of. It is often the case that standard safety requirements of the production environment are not utilized or applied to the build pipeline in the continuous integration environment with containerization or concrete docker. Therefore, the docker registry is often not secured which might result in the theft of the entire company’s source code.

The OWASP DevSecOps Maturity Model provides opportunities to harden DevOps strategies and shows how these can be prioritized.

With the help of DevOps strategies security can also be enhanced. For example, each component such as application libraries and operating system libraries in docker images can be tested for known vulnerabilities.

Attackers are intelligent and creative, equipped with new technologies and purpose. Under the guidance of the forward-looking DevSecOps Maturity Model, appropriate principles and measures are at hand implemented which counteract the attacks.
Container

Install Docker
Run docker pull wurstbrot/dsomm:latest && docker run --rm -p 8080:8080 wurstbrot/dsomm:latest
Browse to http://localhost:8080 (on macOS and Windows browse to http://192.168.99.100:8080 if you are using docker-machine instead of the native docker installation)
For customized DSOMM, take a look at https://github.com/wurstbrot/DevSecOps-MaturityModel-custom. In case you would like to have perform an assessment for multiple teams, iterate from port 8080 to 8XXX, depending of the size of your team.

You can download your current state from the circular headmap and mount it again via docker run -p 8080:8080 -v /tmp/generated.yaml:/usr/share/nginx/html/assets/YAML/generated/generated.yaml wurstbrot/dsomm:latest.

This approach also allows teams to perform self assessment with changes tracked in a repository.

Amazon EC2 Instance

In the EC2 sidenav select Instances and click Launch Instance
In Step 1: Choose an Amazon Machine Image (AMI) choose an Amazon Linux AMI or Amazon Linux 2 AMI
In Step 3: Configure Instance Details unfold Advanced Details and copy the script below into User Data
In Step 6: Configure Security Group add a Rule that opens port 80 for HTTP
Launch your instance
Browse to your instance's public DNS
#!/bin/bash
service docker start
docker run -d -p 80:8080 wurstbrot/dsomm:latest
Information/Data Development

To test changes to the yaml-files, please run:

docker run -ti -v $(pwd)/src/assets/YAML/:/var/www/html/src/assets/YAML wurstbrot/dsomm-yaml-generation
