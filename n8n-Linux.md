# Part #1 : installing Docker in ubuntu:



#### a) Set up Docker's apt repository



 sudo apt update

 sudo apt install ca-certificates curl

 sudo install -m 0755 -d /etc/apt/keyrings

 sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o / etc/apt/keyrings/docker.asc

 sudo chmod a+r /etc/apt/keyrings/docker.asc

 echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo \"${UBUNTU_CODENAME:-&#36;VERSION_CODENAME}\") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

 sudo apt update



#### b) Install the Docker packages



 sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin



#### c) To use the Docker command without sudo



 sudo usermod -aG docker $USER

 \*\*\* Note: After this, log out and log back in or run `newgrp docker` to apply group changes \*\*\*



#### d) Activate Docker Group



 newgrp docker



#### e) Test Docker installation



 docker --version

 docker run hello-world



## -------------------------------------------



# Part #2 : installing n8n in Docker:



#### a) Create Docker Volume for n8n Data



 docker volume create n8n\_data



#### b) Run n8n Interactively (Foreground)



 docker run -it --rm --name n8n -p 5678:5678 -v n8n\_data:/home/node/.n8n docker.n8n.io/n8nio/n8n



#### c) Run n8n in Detached Mode (Background)



 docker run -d --rm --name n8n -p 5678:5678 -v n8n\_data:/home/node/.n8n docker.n8n.io/n8nio/n8n

 docker stop n8n

 docker start n8n

 docker logs -f n8n

