lien dockerhub : https://hub.docker.com/repository/docker/wasmpot/count-server/general

docker pull wasmpot/count-server:latest

docker run -p 8081:80 wasmpot/count-server:latest

Server is running on http://0.0.0.0:8000


##j'ai modifié const port = 8000; dans le .js parce que mon port 8080 etait deja pris