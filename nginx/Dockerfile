# Set the base image to Ubuntu
FROM ubuntu

MAINTAINER Zhiying

RUN apt-get update &&  \
    apt-get install -y \ 
        nginx \
	vim \
    && rm -rf /var/lib/apt/lists/*

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf

# Copy a configuration file from the current directory
ADD nginx.conf /etc/nginx/

# Append "daemon off;" to the configuration file
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Expose ports
EXPOSE 80

# Set the default command to execute when creating a new container
CMD service nginx start
