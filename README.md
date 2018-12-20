https://phptoday.ru/post-preview/gotovim-lokalnuyu-sredu-docker-dlya-razrabotki-na-php

# Перенос docker с диска C на диск D
https://stackoverflow.com/questions/33933107/change-docker-machine-location-windows

This is what worked perfectly for me on Windows 7:
1 Setup the MACHINE_STORAGE_PATH environment variable as the root of the location you want to use for the Docker machines/VMs, cache, etc.
2 Install Docker Toolbox
3 Run Docker Quickstart Terminal

Docker Toolbox will now create all the files at the location pointed at by MACHINE_STORAGE_PATH.

UPDATE:
Note that creating a new VM with the new storage path is not ideal, as the Docker Quickstart Terminal scripts don't seem to work with anything not named "default".
If you've already got a VM sitting in the C: drive, then the simplest thing to do would be to go to Oracle VirtualBox and delete the "default" VM, uninstall Docker Toolbox, delete C:\Users\<username>.docker\, and then follow the 3 steps above.
Note: uninstalling and reinstalling Docker Toolbox may not be required. But I haven't tested without it.

Update
To move Docker certificates also, set the DOCKER_CERT_PATH variable to point to the path of the new drive. Thanks to @Nutle for the tip.


# Запуск
docker-compose up

# Получение ip, по которому можно подключиться
docker-machine ip default

# SSH
docker-machine ls
user: docker
pwd: tcuser

Connect to need container:
docker ps
sudo docker exec -i -t 665b4a1e17b6 /bin/bash #by ID

# Phpmyadmin
192.168.99.100
root
root


