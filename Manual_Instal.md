# Pi Manual Install Instructions
Attunement uses docker containers to run the various functions

## Upgrade Pi
`sudo apt-get update`
`sudo apt-get dist-upgrade`

## Setup docker
`sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release`
`curl -fsSL https://get.docker.com -o get-docker.sh`
`sudo sh get-docker.sh`
`sudo groupadd docker`
`sudo usermod -aG docker $USER`
`newgrp docker`
`docker run hello-world`
`sudo systemctl enable docker.service`
`sudo systemctl enable containerd.service`

## Install Node Red In Docker
`docker run -it -p 1880:1880 -v /home/pi/node-red:/data --name attuneNodeRed nodered/node-red:latest`
`docker start attuneNodeRed`
`docker update --restart unless-stopped attuneNodeRed`

## Download Nodejs
`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`
`sudo apt-get install -y nodejs`

## Get stored copy of the webserver
git copy web server

## Allows bidirectional communictaion in real time i.e. button presses
`npm install socket.io`

## enables the use of port 80 without root
`sudo apt-get install libcap2-bin`
``sudo setcap cap_net_bind_service=+ep `readlink -f \`which node\` ` ``

## Install PM2 and setup
Used to manage NodeJS server. Will be moved to docker enviroment
`sudo npm install pm2 -g`
`sudo env PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u pi --hp /home/pi`
`pm2 node /home/pi/web/webserver.js`
`pm2 save`
