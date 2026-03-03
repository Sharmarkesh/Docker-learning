# Deploying a  Website with Docker and Nginx

# Step 1: Create Project Structure

NginxDocker/
     ->DjibsecWeb
         index.html
         style.css
     -> Dockerfile
![](FilesCreation.png)

# Step 2: Create the Dockerfile

Here’s the Dockerfile  and what this does:

#Docker Author name <br>
LABEL author="Sharmaarke Sharif"

#Uses a minimal Nginx image based on Alpine  Ubuntu <br>
FROM ubuntu:latest

#Run update and install nginx <br>
RUN apt-get -y update && apt-get -y install nginx

#Adds your index.html file to the Nginx web root <br>
COPY DjibsecWeb/index.html /var/www/html/index.nginx-debian.html

#Adds your style.css file to the Nginx web root <br>
COPY DjibsecWeb/style.css /var/www/html/

#Makes the container’s HTTP port available to the host <br>
EXPOSE 80

#Keeps Nginx running in the foreground
CMD ["nginx", "-g", "daemon off;"]

![](dockerScript.png)

# Step 3: Build the Docker Image

docker build -t djibsec-web.

![] (dockerBuild.png)



# Step 4: Run the Container

docker run -d -p 80:80 djibsec.com
![](ContainerRun.png)

# Step 5: Visit http://localhost:80 
![](Webapp.png)
