+++
date = 2020-04-13T04:00:00Z
tags = ["docker", "mysql", "mariadb"]
title = "Importing a database into a Docker container"

+++
Importing a database into a running MariaDB/MySQL container is a straight forward process.

Before you begin, open up you MySQL CLI and provision an empty database.

    docker exec -it <container_id> mysql -u<user> -p<password>

Make sure to create your blank database.

    create database something_unique;

Open up a terminal and cd into the directory that contains your .db file you'd like to import.

Run the following:

    docker exec -i <container_id> mysql -u<user> -p<password> <your-empty-db-here> <your-local-db-file-here>	

The `-i` flag allows docker to execute with STDIN, which in this case is your db file.

That's it. You've now got your db freshly loaded and ready to use.