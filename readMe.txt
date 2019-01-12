#docker stack deploy -c stack.yml mysql
#docker run --name mysql_container -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -e MYSQL_PASSWORD=password -p 3306:3306 -d mysql/mysql-server
#docker run -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -e MYSQL_PASSWORD=password -p 3306:3306 -d mysql/mysql-server
#docker run --mount type=bind,src=D:/docker/tmp/mysql/my.cnf,dst=/etc/my.cnf --mount type=bind,src=D:/docker/tmp/mysql/datadir,dst=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -e MYSQL_PASSWORD=password -p 3306:3306 -d  mysql/mysql-server
#docker run --name=mysql2 --mount type=bind,src=D:/docker/tmp/mysql/my.cnf,dst=/etc/my.cnf --mount type=bind,src=D:/docker/tmp/mysql/datadir,dst=/var/lib/mysql -d mysql/mysql-server
#docker run --volumes-from mysql_data -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -v D:/docker/tmp/mysql/datadir:/var/lib/mysql -e MYSQL_PASSWORD=password -p 3306:3306 mysql
#docker create --name mysql_data -v D:/docker/tmp/mysql/datadir mysql-data-container
#docker run --volumes-from mysql_data -v D:/docker/tmp/mysql/datadir:/var/lib/mysql -e MYSQL_USER=mysql -e MYSQL_PASSWORD=mysql -e MYSQL_DATABASE=sample -e MYSQL_ROOT_PASSWORD=supersecret -it -p 3306:3306 mysql

http://blog.arungupta.me/docker-mysql-persistence/





For Windows
docker create --name mysql_data -v D:/docker/tmp/mysql/datadir mysql-data-container

docker run --volumes-from mysql_data -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -v D:/docker/tmp/mysql/datadir:/var/lib/mysql -e MYSQL_PASSWORD=password -p 3306:3306 mysql


For Linux
docker create --name mysql_data -v /mnt/hgfs/D/ubuntu/data mysql-data-container
docker run -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=app1 -e MYSQL_USER=user -v /mnt/hgfs/D/ubuntu/data:/var/lib/mysql -e MYSQL_PASSWORD=password -p 3306:3306 mysql
