# exploring-docker


Ubuntu Docker host (https://docs.docker.com/engine/install/ubuntu/)
```bash
#uninstall older versions
sudo apt-get remove docker docker-engine docker.io containerd runc

#update and install initial tools
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

#add docker oficial key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

#verify key
sudo apt-key fingerprint 0EBFCD88

#add repository
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

#install docker
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo usermod -aG docker $USER

sudo apt-get install -y python3 python3-pip
pip3 install --user docker-compose

#start docker daemon service
sudo service docker start
sudo update-rc.d docker defaults

#run hello world
sudo docker run hello-world

#echo -n "plain text" | base64
```

# Notes

Since I am running ubuntu on WSL, I will also need to install docker desktop on windows.

You can use docker to run official images or you can use a dockerfile to build a custom image.
You can also define volume to places of the host to facilitate development.
Using dockerfile, you can merge dev files to build an actual image.

Make sure to use .dockerignore file including node modules, git, etc. Make sure to use caching of modules before adding the whole content.
We can rely on alpine linux version for smaller images.

Use kubernetes to manage and facilitate management and scale.
