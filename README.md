# DevSecOps-Project-

Introduction:

From a startup to a multinational corporation the software development industry is currently dominated by agile frameworks and product teams and as part of it DevOps strategies. It has been observed that during the implementation, security aspects are usually neglected or are at least not sufficient taken account of. It is often the case that standard safety requirements of the production environment are not utilized or applied to the build pipeline in the continuous integration environment with containerization or concrete docker. Therefore, the docker registry is often not secured which might result in the theft of the entire company’s source code.

With the help of DevOps strategies security can also be enhanced. For example, each component such as application libraries and operating system libraries in docker images can be tested for known vulnerabilities.

Attackers are intelligent and creative, equipped with new technologies and purpose. Under the guidance of the forward-looking DevSecOps Maturity Model, appropriate principles and measures are at hand implemented which counteract the attacks.

Information/Data Development:
To test changes to the yaml-files, please run:

docker run -ti -v $(pwd)/src/assets/YAML/:/var/www/html/src/assets/YAML wurstbrot/dsomm-yaml-generation
