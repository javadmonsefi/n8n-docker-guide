# **Part #1 : installing Docker in Windows:**





#### a) Download Docker Desktop Using the Link Below and Install it



https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm\_source=docker\&utm\_medium=webreferral\&utm\_campaign=docs-driven-download-win-amd64\&\_gl=1\*1jetdxw\*\_gcl\_au\*MTUzOTk5MjA0NS4xNzU2MTQ2MDU1\*\_ga\*MTU0OTEwODc3MS4xNzU2MTQ1Nzk1\*\_ga\_XJWPQMJYHQ\*czE3NTY1MDM1MjIkbzckZzEkdDE3NTY1MDM1NTMkajI5JGwwJGgw



\*\* Note: update wsl using this command -> wsl --update \*\*





#### b) Restart your system





#### c) Open Docker Desktop and make sure the Docker Engine is running



-------------------------------------------------------------------------------------------------------------------------------



# Part #2 : installing n8n in Docker:





#### a) Create Docker Volume for n8n Data



docker volume create n8n\_data





#### b) Run n8n Interactively (Foreground)



docker run -it --rm --name n8n -p 5678:5678 -v n8n\_data:/home/node/.n8n docker.n8n.io/n8nio/n8n



\*\* DNS: 178.22.122.100 185.51.200.2 \*\*





#### c) Run n8n in Detached Mode (Background)



docker run -d --rm --name n8n -p 5678:5678 -v n8n\_data:/home/node/.n8n docker.n8n.io/n8nio/n8n



docker stop n8n



docker start n8n



docker logs -f n8n

