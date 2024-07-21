# Install ERPNEXT VERSION 15

# Steps
. create Folder <folder_name>
. create Folder called erpnext_docker in this folder
. download docker-compose.yml in this folder
. sudo docker stop $(sudo docker ps -q)
. sudo docker rm $(sudo docker ps -a -q)
. sudo docker rmi $(sudo docker images -q)
. sudo docker volume rm $(sudo docker volume ls -q)
. sudo docker compose -p pwd -f docker-compose.yml up

# Install app on erpnext

. sudo docker exec -it --user root <frontend_container_name> bash
. su - frappe
. cd /home/frappe/frappe-bench
. bench get-app hrms
. bench --site frontend install-app hrms
. bench --site frontend migrate
. sudo docker compose -p pwd -f docker-compose.yml up
