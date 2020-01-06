# Multiple WordPress containers using Docker Compose

This repo contains some scripts to allow running multiple WordPress containers on a single VPS using Docker Compose. It will also handle acquiring, renewing, and using HTTPs certificates from Let's Encrypt. It uses the [nginx-proxy](https://github.com/jwilder/nginx-proxy) and [docker-letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion) Docker images. 



To use the scripts (assuming you have already downloaded and setup Docker and Docker Compose), do the following:

1. Clone the repo: `git clone https://github.com/arnath/multiple-wordpress-containers.git`

2. Replace the values in the .env file with the settings for your sites. 

3. Navigate to the directory of the docker-compose.yml file.

4. Start the containers in detached mode: `docker-compose up -d`



To add additional sites, do the following:

1. Copy the wp-site1 service block in docker-compose.yml and rename all the instances of "site1" to the name of your new site. 

2. Add the volume you defined in the service block to the top-level volumes section at the bottom of docker-compose.yml. 

3. Add environment settings for your new site to the .env file. 

4. Copy one of the lines in mariadb/init.sh and replace the site1 or site2 environment variables with the new ones you defined in step 3. 
