
# Flask REStful API demo

## DB Set up

CREATE TABLE product (
	id INTEGER NOT NULL AUTO_INCREMENT,
	name VARCHAR(100),
	description VARCHAR(200),
	price FLOAT,
	qty INTEGER,
	PRIMARY KEY (id),
	UNIQUE (name)
);

## Running the application

```
cd flask_product_api
export FLASK_APP=product_api
export FLASK_ENV=development
flask run
```
## URLs

POST http://127.0.0.1:5000/product
GET http://127.0.0.1:5000/product
PUT http://127.0.0.1:5000/product/<product_id>
DELETE http://127.0.0.1:5000/product/<product_id>

**Swagger UI**

http://127.0.0.1:5000/apidocs/index.html 

# Docker 

docker build -t docker_flask_app .

docker run -p 5000:5000 -d \
--name my_container_flask \
docker_flask_app

docker logs my_container_flask -f

docker container stop my_container_flask
docker container rm my_container_flask
docker image rm docker_flask_app

docker exec -it my_container_flask bash

References
==========

**Swagger**

https://github.com/flasgger/flasgger/blob/master/examples/apispec_example.py ( Imp )

https://swagger.io/docs/specification/2-0/describing-request-body/
https://swagger.io/docs/specification/describing-request-body/ ( v3 )
http://brunorocha.org/python/flask/flasgger-api-playground-with-flask-and-swagger-ui.html

**Docker**

https://dev.to/riverfount/dockerize-a-flask-app-17ag

