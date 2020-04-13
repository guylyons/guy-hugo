+++
date = 2020-04-13T04:00:00Z
tags = ["docker", "mysql", "mariadb"]
title = "Importing a database into a Docker container"

+++
![](/uploads/shutterstock_1378652867.jpg)

Importing a database into a running MariaDB/MySQL container is a straight forward process.

1) First, you'll need to run the MySQL CLI and provision an empty database.

    docker exec -it <container_id> mysql -u<user> -p<password>

2) Create your blank database.

    create database something_unique;

Open up a terminal and cd into the directory that contains your .db file you'd like to import.

3) Run the following:

    docker exec -i <container_id> mysql -u<user> -p<password> <your-empty-db-here> <your-local-db-file-here>	

The `-i` flag allows docker to execute with STDIN, which in this case is your db file.

That's it. You've now got your db freshly loaded and ready to use.