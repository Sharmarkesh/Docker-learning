#Docker Author name 
LABEL author="Sharmaarke Sharif"
#Uses a minimal Nginx image based on Alpine  Uuntu
FROM ubuntu:latest

#Run update and install nginx
RUN apt-get -y update && apt-get -y install nginx
#Adds your index.html file to the Nginx web root
COPY DjibsecWeb/index.html /var/www/html/index.nginx-debian.html
#Adds your style.css file to the Nginx web root
COPY DjibsecWeb/style.css /var/www/html/
#Makes the container’s HTTP port available to the host
EXPOSE 80
#Keeps Nginx running in the foreground
CMD ["nginx", "-g", "daemon off;"]