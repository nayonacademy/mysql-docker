# how to install 
- git clone https://github.com/nayonacademy/mysql-docker.git
- cd mysql-docker
- docker-compose up -d

# how to connect with mysql
- mysql -h 127.0.0.1 -u user -P 3306 -p
- pass: password

# How to connect with mysqlworkbench

Host : 127.0.0.1

port : 3306

username : user

password : password

# Create a mysql instance in docker-compose - Tutorial

	## Why need Docker Compose?
		Docker compose is a very easy solution. It will create a container and run ours code. This tutorial is only show you how to Create a single container and run [MySQL](https://www.mysql.com/) instance easily 


	## Docker installatin :
		I write a blog how to install docker in Linux machine It will help to install
		[Docker install instruction](https://nayon.net/docker-install-ubuntu/)


		After install check the docker work correctly or not
		- docker-compose --version

	## Write a docker-compose file for mysql
		After installing docker and run it will will write a docker compose file.
		create a directory "mysql-docker" and inside the folder create docker-compose.yml

		```yml
			version: '3.3'
			services:
			  db:
			    image: mysql:5.7
			    restart: always
			    environment:
			      MYSQL_DATABASE: 'db'
			      # So you don't have to use root, but you can if you like
			      MYSQL_USER: 'user'
			      # You can use whatever password you like
			      MYSQL_PASSWORD: 'password'
			      # Password for root access
			      MYSQL_ROOT_PASSWORD: 'password'
			    ports:
			      # <Port exposed> : < MySQL Port running inside container>
			      - '3306:3306'
			    expose:
			      # Opens port 3306 on the container
			      - '3306'
			      # Where our data will be persisted
			    volumes:
			      - my-db:/var/lib/mysql
			# Names our volume
			volumes:
			  my-db:

		```	  
