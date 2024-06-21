build:
	docker build -t gennadii87/img-db:mysql8.0-lts .

run:
	docker run -d --name mysql-container -v my_mysql_data:/var/lib/mysql -p 3307:3306  gennadii87/img-db:mysql8.0-lts

stop:
	docker stop mysql-container