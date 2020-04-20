+++
date = 2020-04-13T04:00:00Z
draft = true
tags = ["wordpress", "docker", "vscode", "xdebug"]
title = "Configuring xdebug with WordPress, Docker and VS Code"

+++
![docker.png](../docker.png)

Sometimes configuration for debugging your stack can be a pain.

Explain how to configure the Dockerfile

also maybe this: [https://github.com/JPeer264/wordpress-docker-vscode-xdebug-boilerplate/blob/master/.docker/cms/Dockerfile](https://github.com/JPeer264/wordpress-docker-vscode-xdebug-boilerplate/blob/master/.docker/cms/Dockerfile "https://github.com/JPeer264/wordpress-docker-vscode-xdebug-boilerplate/blob/master/.docker/cms/Dockerfile")

    FROM wordpress:latest
    MAINTAINER guylyons2@gmail.com
    
    # install and configure XDebug
    RUN yes | pecl install xdebug \
        && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
        && echo "xdebug.remote_enable=1" >> /usr/local/etc/php/conf.d/xdebug.ini \
        && echo "xdebug.remote_autostart=1" >> /usr/local/etc/php/conf.d/xdebug.ini \
        && echo "xdebug.profiler_enable=1" >> /usr/local/etc/php/conf.d/xdebug.ini \
        && echo "xdebug.profiler_output_name=cachegrind.out.%t" >> /usr/local/etc/php/conf.d/xdebug.ini \
        && echo "xdebug.profiler_output_dir=/tmp" >> /usr/local/etc/php/conf.d/xdebug.ini \
        && rm -rf /usr/local/etc/php/conf.d/opcache-recommended.ini

Explain how to configure VS Code

    {
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Listen for XDebug",
                "type": "php",
                "request": "launch",
                "port": 9000,
                "pathMappings": {
                    "/var/www/html": "${workspaceRoot}"
                }
            },
            {
                "name": "Launch currently open script",
                "type": "php",
                "request": "launch",
                "program": "${file}",
                "cwd": "${fileDirname}",
                "port": 9000
            }
        ]
    }
