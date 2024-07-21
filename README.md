# Install ERPNEXT VERSION 15

# Steps
. create Folder <folder_name> <br/>
. create Folder called erpnext_docker in this folder <br/>
. download docker-compose.yml in this folder <br/>
. sudo docker stop $(sudo docker ps -q) <br/>
. sudo docker rm $(sudo docker ps -a -q) <br/>
. sudo docker rmi $(sudo docker images -q) <br/>
. sudo docker volume rm $(sudo docker volume ls -q) <br/> 
. sudo docker compose -p pwd -f docker-compose.yml up <br/>

# Install app on erpnext

. sudo docker exec -it --user root <frontend_container_name> bash
. su - frappe
. cd /home/frappe/frappe-bench
. bench get-app hrms
. bench --site frontend install-app hrms
. bench --site frontend migrate
. sudo docker compose -p pwd -f docker-compose.yml up
