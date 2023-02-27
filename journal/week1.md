# Week 1 — App Containerization

### Containerize Backend
Created a backend Dockerfile by first taking the python3 base image from Docker hub. The next layer to be installed is flask and flask-cors from the requirements.txt.
Built the container by running app.py using flask and ran the container by setting the Backend and Frontend urls as environment variables using - e option.
docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask.
Initially got the following error on opening browser on port 4567

![backenderror](https://user-images.githubusercontent.com/123596308/221493666-6e05a3ef-2a7e-4de6-9486-bacd6524983b.png)

Two endpoint functions withe same name, so resolved by changing the function name.

### Containerize Frontend

Created a Dockerfile, build and ran the Frontend container on port 3000.

### Multiple containers with Docker Compose(Frontend, Backend, DynamoDB, Postgres

Compose is a tool for defining and running multi-container Docker applications. With Compose, we use a YAML file to configure application’s services. Then, with a single command, we can create and start all the services from our configuration. Modified the docker-compose.yml to build and run all the containers.

### Created an endpoint for notifications and added functionality by creating a react page to display notifications.

![endpoint](https://user-images.githubusercontent.com/123596308/221498035-c5118d2a-144c-4a3c-852f-29217dd258ea.png)

![notifications](https://user-images.githubusercontent.com/123596308/221498150-3c2373c7-1c7a-4b52-8173-dcf362be6949.png)

### Pushing image to DockerHub

Created new repository in Docker Hub and pushed backend-flask image to it.

![image](https://user-images.githubusercontent.com/123596308/221498652-2b0ac16d-75f8-427d-81e0-89799e13ee72.png)

Initially got the error "Docker denied: requested access to the resource is denied". Changed my private repository to public and tried again and got the same error.
Finally on googling, it was suggested to logout and login again. So logged out of docker in gitpod terminal and looged into docker in gitpod with the docker credentials and was able to push the image.

Link to the Solution
https://www.biostars.org/p/9531985/#:~:text=Solution%201%3A%20First%2C%20check%20your,log%20in%20using%20your%20credentials.&text=In%20some%20cases%2C%20this%20solution%20might%20work.





