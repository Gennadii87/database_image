build:
	docker build -t gennadii87/img-db:postgers15.1-alpine .

run:
	docker run -d --rm --name my-postgres-container -v pgdata:/var/lib/postgresql/data -p 5434:5432  gennadii87/img-db:postgers15.1-alpine

stop:
	docker stop my-postgres-container