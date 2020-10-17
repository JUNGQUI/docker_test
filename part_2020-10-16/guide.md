#### 특정 volume 생성 후 volume container 만들기
docker image build -t example/mysql-data:latest .
docker container run -d --name mysql-data example/mysql-data:latest

#### mysql image pull 후 mysql container run
docker container run -d -p 3306:3306 --name jklee_mysql -e "MYSQL_ALLOW_EMPTY_PASSWORD=true" -e "MYSQL_DATABASE=volume_test" -e "MYSQL_USER=example" -e "MYSQL_PASSWORD=example" --volumes-from mysql-data mysql:8.0.17

#### 이후 intellij 를 통해서 접근 가능, 또한
docker exec -it jklee_mysql mysql -u root -p volume_test
#### 를 통해서도 접근 가능


