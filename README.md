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

#start docker daemon service
sudo service docker start

#run hello world
sudo docker run hello-world
```

